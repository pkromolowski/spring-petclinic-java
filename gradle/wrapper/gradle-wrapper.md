## Documentation of `gradle-wrapper.properties`

This file configures the Gradle wrapper for a project. The Gradle wrapper allows you to execute Gradle build tasks without installing Gradle globally on your system.

**Key Variables and their Descriptions:**

* **`distributionBase`:**  Sets the base directory where Gradle distributions will be stored. Defaults to `GRADLE_USER_HOME` which typically points to the user's home directory.
* **`distributionPath`:** Specifies the subdirectory within `distributionBase` where Gradle distributions will be located. Here, it's set to `wrapper/dists`.
* **`distributionUrl`:** Defines the URL from which to download the Gradle distribution. In this case, it points to `https://services.gradle.org/distributions/gradle-8.7-bin.zip`, downloading Gradle version 8.7.
* **`networkTimeout`:** Sets a timeout (in milliseconds) for network requests when downloading the Gradle distribution.  A value of `10000` means a 10-second timeout.
* **`validateDistributionUrl`:** Determines whether to validate the downloaded Gradle distribution against the specified URL. If set to `true` (as it is here), the downloaded file is checked for integrity.
* **`zipStoreBase`:**  Similar to `distributionBase`, but specifies the base directory for storing downloaded Gradle ZIP files. Defaults to `GRADLE_USER_HOME`.
* **`zipStorePath`:** Defines the subdirectory within `zipStoreBase` where downloaded ZIP files will be stored. Here, it's set to `wrapper/dists`.

**Assumptions and Dependencies:**

* **Internet Connection:** This script assumes an active internet connection to download the Gradle distribution.
* **`GRADLE_USER_HOME` Environment Variable:**  The script relies on the `GRADLE_USER_HOME` environment variable being set correctly. This variable typically points to the user's home directory.



**Pseudo Code:**

1. **Set Variables:**
   - Define `distributionBase` as `GRADLE_USER_HOME`.
   - Define `distributionPath` as `wrapper/dists`.
   - Define `distributionUrl` as `https://services.gradle.org/distributions/gradle-8.7-bin.zip`.
   - Define `networkTimeout` as `10000`.
   - Define `validateDistributionUrl` as `true`.
   - Define `zipStoreBase` as `GRADLE_USER_HOME`.
   - Define `zipStorePath` as `wrapper/dists`.

2. **Download Gradle Distribution:**
   - Use the `distributionUrl` to download the Gradle distribution (version 8.7) to the `zipStorePath` directory.
   - Ensure the downloaded file is validated against the `distributionUrl` for integrity.

3. **Store Downloaded Distribution:**
   - Store the downloaded Gradle distribution in the `distributionPath` directory within `distributionBase`.



