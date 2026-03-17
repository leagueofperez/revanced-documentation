Installing RVX Builder for the first time
==

1. Install [Termux](https://f-droid.org/packages/com.termux/).

2. Open Termux and run:

```
curl -L "https://raw.githubusercontent.com/leagueofperez/rvx-builder/refs/heads/revanced-extended/android-interface.sh" | bash
```

> [!TIP]
>
> If your remote `.env` causes issues, run:
>
> ```
> curl -L "https://raw.githubusercontent.com/leagueofperez/rvx-builder/refs/heads/revanced-extended/android-interface.sh" | LOAD_REMOTE_ENV=0 bash
> ```

> [!NOTE]
>
> With `curl | bash`, rvx-builder is installed by default in `~/rvx-builder`.

After installing, rvx-builder will run automatically.


Using RVX Builder (Termux)
==

> [!NOTE]
> ### If you are preparing to install in a ROOT environment:
>
> Follow the steps on [this page](https://github.com/leagueofperez/revanced-documentation/blob/main/docs/supplying-an-apk.md) to prepare the device for a mount installation. Note that the APK from APKMirror that you install must be the same version as the APK you will patch.
>
> Also, Termux must have superuser permissions granted.


1. Run rvx-builder in Termux:

```
cd ~/rvx-builder
bash android-interface.sh run
```

2. A GUI will open in your browser. Click `Start patching`. After the dependencies are downloaded, click `Continue`.

3. Select the app you want to patch, or upload the APK.

4. Select the patches you want to include.

- Read [this document](https://github.com/leagueofperez/revanced-documentation/blob/main/docs/information-about-patches.md) for information on patches you may want to include or exclude. Otherwise, just click the `Select All` button to select all Default patches.

> [!IMPORTANT]
> For ROOT YouTube / YT Music installations, the `GmsCore support` patch must be excluded. In non-ROOT environments the patch will be hidden and included automatically.

5. If you did not upload an APK in step 3, a menu will appear where you can choose the version of the app to patch. Select the first option, marked `(AUTO SELECTION)`, or select a version marked as `(suggested)`. After the APK is downloaded, click `Continue` and wait for patching to complete.

6. For non-ROOT installations, the patched APK will be saved to your device and it must be manually installed. The path to the APK will be displayed at the bottom of the patch log. For ROOT installations, the app will be mounted automatically.

> [!TIP]
> For ROOT installations, I recommend also installing the [Detach Magisk module](https://forum.xda-developers.com/t/module-detach3-detach-market-links.3447494/). It prevents automatic updates from the Google Play Store, which would cause crashes to occur in the ROOT environment.


Additional info
==

### Updating rvx-builder:

```
cd ~/rvx-builder
bash android-interface.sh update
```

### Reinstalling rvx-builder:

```
cd ~/rvx-builder
bash android-interface.sh reinstall
```

### Configuring `.env` / Java in Termux:

- You can set `JDK_VERSION_ANDROID` in `~/rvx-builder/.env`.
- Example value: `JDK_VERSION_ANDROID=openjdk-25`.


Troubleshooting
==
**1. If encountering an error when installing rvx-builder for the first time:**

- Ensure that Termux is not the Play Store version of Termux.
- Try reinstalling Termux.
- Try changing networks and disabling any VPN / adblockers.
- Try changing mirrors with `termux-change-repo`.

**2. If rvx-builder worked in the past, but an issue occurred when using it again:**

```
cd ~/rvx-builder
bash android-interface.sh reinstall
```

**3. If an issue occurs during the patching process:**

- Ensure that Termux has battery optimization exclusions.
- Reinstall rvx-builder:

```
cd ~/rvx-builder
bash android-interface.sh reinstall
```

___
- If you encounter any other issues, please report them on the [GitHub issues page](https://github.com/leagueofperez/rvx-builder/issues).
