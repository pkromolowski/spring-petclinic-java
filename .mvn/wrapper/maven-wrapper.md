## Documentation of `maven-wrapper.properties`

This file configures the Maven wrapper for a project. The Maven wrapper allows you to execute Maven build tasks without installing Maven globally on your system.

**Key Variables and their Descriptions:**

* **`wrapperVersion`:** Specifies the version of the Maven wrapper to use. In this case, it's set to `3.3.2`.
* **`distributionType`:** Defines the type of Maven distribution to download. Here, it's set to `only-script`, indicating that only the script files are downloaded, not the full Maven installation.
* **`distributionUrl`:** Specifies the URL from which to download the Maven distribution. In this case, it points to `https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.7/apache-maven-3.9.7-bin.zip`, downloading Maven version 3.9.7.

**Assumptions and Dependencies:**

* **Internet Connection:** This script assumes an active internet connection to download the Maven distribution.

**Pseudo Code:**

1. **Set Variables:**
   - Define `wrapperVersion` as `3.3.2`.
   - Define `distributionType` as `only-script`.
   - Define `distributionUrl` as `https://repo.maven.apache.org/maven2/org/apache/maven/apache-maven/3.9.7/apache-maven-3.9.7-bin.zip`.

2. **Download Maven Distribution:**
   - Use the `distributionUrl` to download the specified Maven distribution (version 3.9.7) as a script-only package.



