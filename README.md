# Trade OS Android Releases

Official public download repository for the Trade OS Android APK.

## Permanent links

Latest APK:

`https://github.com/iamhizbi/trade-os-releases/releases/latest/download/trade-os.apk`

Latest version metadata:

`https://raw.githubusercontent.com/iamhizbi/trade-os-releases/main/latest.json`

## Publish a new APK

1. Build the APK with Expo EAS.
2. Copy the direct APK download URL from the completed EAS build.
3. Open this repository on GitHub.
4. Open **Actions**.
5. Select **Publish Trade OS APK**.
6. Choose **Run workflow**.
7. Enter the version, version code, APK URL, update type, and release notes.
8. Run the workflow.

The workflow automatically:

- downloads the APK;
- validates that it is an Android APK archive;
- renames it to `trade-os.apk`;
- generates `trade-os.apk.sha256`;
- publishes a GitHub Release;
- updates `latest.json`;
- commits the new metadata back to `main`.

## Android update rules

Every native release must keep the same:

- Android package/application ID;
- Android signing certificate.

Every new release must increase:

- Expo `version`;
- Android `versionCode`.

Most Trade OS web interface changes deploy through Vercel and do not require a new APK. Publish a new APK only for native changes such as notification actions, notification/launcher icons, Android permissions, or native Expo dependencies.

## Security

Never commit:

- `.env` files;
- API keys;
- Android signing credentials;
- service-account files;
- private source code.
