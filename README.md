# Setup: Docu-notion + docusaurus

#### Host specs:

Ubuntu 20.04

#### Software specs:

- NodeJS `[v21.4.0]`
- npm `[v10.2.4]`
- yarn `[v1.22.21]`

## NodeJS installation

1. **Create a Temporary Directory:**

```bash
mkdir -p ~/tmp && cd ~/tmp 
```

2. **Download NodeJS:** 

```bash
wget https://nodejs.org/dist/v21.4.0/node-v21.4.0-linux-x64.tar.xz
```

3. **Unpack NodeJS and Set Environment Variables:**
   * Use one of the following methods:
    * **Method A (Persistent Environment Variables):**
        ```bash
        sudo mkdir -p /usr/local/lib/nodejs
        sudo tar -xJvf node-v21.4.0-linux-x64.tar.xz -C /usr/local/lib/nodejs
        echo 'export NODEJS_HOME=/usr/local/lib/nodejs/node-v21.4.0-linux-x64' | sudo tee -a /etc/profile
        echo 'export PATH=$NODEJS_HOME/bin:$PATH' | sudo tee -a /etc/profile
        source /etc/profile
        ```
    
    * **Method B (Temporary Environment Variables):**
        ```bash
        sudo mkdir -p /usr/local/lib/nodejs
        sudo tar -xJvf node-v21.4.0-linux-x64.tar.xz -C /usr/local/lib/nodejs
        echo 'export NODEJS_HOME=/usr/local/lib/nodejs/node-v21.4.0-linux-x64' | sudo tee -a /etc/profile
        echo 'export PATH=$NODEJS_HOME/bin:$PATH' | sudo tee -a /etc/profile
        source /etc/profile
        ```

4. **Install yarn:**

```bash
npm install --global yarn
```

5. **Check Installed Versions:**

```bash
node -v
npm -v
yarn -v
```

## Clone and Prepare Repository for Docusaurus

1. **Clone the Repository:**

```bash
cd ~/tmp
git clone https://github.com/sillsdev/docu-notion-sample-site.git
```

2. **Set Notion API Token and Root Page:**
    * Replace *** with your Notion token and root page.
    * **Set Environment Variables:**
    ```bash
    export DOCU_NOTION_SAMPLE_ROOT_PAGE=[***]
    export DOCU_NOTION_INTEGRATION_TOKEN=[***]
    ```
    * Source: [Notion integration](https://developers.notion.com/docs/create-a-notion-integration#give-your-integration-page-permissions)

3. **Install Dependencies:**
```bash
npm install
```

4. **Parse Pages with docu-notion:**

```bash
npx docu-notion -n $DOCU_NOTION_INTEGRATION_TOKEN -r $DOCU_NOTION_SAMPLE_ROOT_PAGE
```

## Starting Docusaurus Server

1. **Navigate to the Project Directory:**
2. **Start the Docusaurus Server:**
```bash
yarn start
```
* Source [Docusaurus Intallation Guide](https://docusaurus.io/docs/installation)

