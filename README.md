This repo contains the source code `index.html` for our website https://openmachine.ai/

### Notes
- Quick preview: try one of the following options
  - https://htmlpreview.github.io/?https://github.com/OpenMachine-ai/openmachine-ai.github.io/blob/main/index.html
  - https://htmlpreview.github.io/?https://openmachine-ai.github.io
  - https://htmlpreview.github.io/
- You can see our GitHub pages here: https://openmachine-ai.github.io
- Google search console with details about indexing and search impressions: [[Console]](https://search.google.com/search-console?resource_id=sc-domain%3Aopenmachine.ai&hl=en), [[Milestones]](https://search.google.com/search-console/insights/achievements?resource_id=sc-domain:openmachine.ai)

### Latest notes on how we generated the latest `index.html`
  - Created the website in Mozilla soloist.ai at https://soloist.ai/openmachine
  - Unfortunately, the website loads very slowly when hosted on soloist.ai.
  - To export the website and host on GitHub: Unfortunately, soloist doesn't have an export feature. Therefore, open [the website](https://soloist.ai/openmachine) in Chrome browser and save it via `Menu -> File -> Save Page As .. -> Webpage complete`: This downloads a folder called `OpenMachine_files` and a file `OpenMachine.html`. Then stored the folder and the file in this github repo.
  - Then copy the file to `index.html` and replace `soloist.ai/openmachine` by `openmachine.ai` as follows:
    ```bash
    cp OpenMachine.html index.html
    sed -i .bak 's:soloist.ai/openmachine:openmachine.ai:g' index.html
    ```
  - In case there are any issues with this, you can always switch back to the old, hand-made site as follows:
    ```bash
    rm index.html
    cp index_hand-made.html index.html
    ```
  - soloist.ai is very limited, perhaps try https://webstudio.is/, which is open-source and you can export a static website, see here https://docs.webstudio.is/university/self-hosting#static-site

### Hosting
Hosting is done via GitHub Pages (because it's free). And we use namecheap for our domain name:
- Setup on namecheap:
  - navigate to the `Domain List` and click on `Manage` to the far right of your domain name.
  - Then click on the `Advanced DNS` tab. Click `Add New Record` to add the following five records:

     | Type         | Host | Value                    | TTL       |
     |--------------|------|--------------------------|-----------|
     | CNAME Record | www  | openmachine-ai.github.io | Automatic |
     | A Record     | @    | 185.199.108.153          | Automatic |
     | A Record     | @    | 185.199.109.153          | Automatic |
     | A Record     | @    | 185.199.110.153          | Automatic |
     | A Record     | @    | 185.199.111.153          | Automatic |
- For more details see https://dev.to/pauljwil/connect-github-pages-to-your-namecheap-domain-4gjj
