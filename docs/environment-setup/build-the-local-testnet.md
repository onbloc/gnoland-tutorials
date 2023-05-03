# Build the Local Testnet

## Prerequisites

- [Initial Setup](../environment-setup/initial-setup.md)

### Step 1. Run a Local Node

Start a local Gnoland blockchain node with the following command:

```bash
gnoland
```

<figure><img src="../../.gitbook/assets/05_run_gnoland.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/06_follow_gnoland.png" alt=""><figcaption></figcaption></figure>

After a few moments, you will start to see blocks being produced on your network.

### Step 3. Build a Web Page (Optional)

This section will teach you how to launch your own gno.land web page that will serve as a docs page for your network. Although this section is optional, we highly recommend completing it.

#### Prerequisites

- [Initial Setup - Build gnoweb](../environment-setup/initial-setup.md#build-gnoweb)

Run the web page with the following command:

```
gnoweb
```

<figure><img src="../../.gitbook/assets/07_build_run_gnoweb.png" alt=""><figcaption></figcaption></figure>

To confirm that your web page is running on your network, use a browser to access the following link:

{% embed url="http://localhost:8888" %}

<figure><img src="../../.gitbook/assets/08_webpage.png" alt=""><figcaption></figcaption></figure>

Under the **Explore new packages.** section, you will see a list of pre-built realms and packages that are already deployed on your network. You may click on each one to view its details.
