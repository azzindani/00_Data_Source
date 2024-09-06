<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-this-repository">About This Repository</a>
    </li>
    <li>
      <a href="#import-dataset">Import Dataset</a>
      <ul>
        <li><a href="#import-by-url">Import by URL</a></li>
        <li><a href="#download-datasets">Download Datasets</a></li>
        <li><a href="#download-all-datasets">Download All Datasets</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

## About This Repository

This repository contain datasets that can be used for data analytics, machine learning, deep learning, etc. The file format used are csv, zip, json, geojson, etc. These datasets came from different source such as kaggle, github, etc. You may not found large datasets over 25 MB, because of github limitation.

My purpose to collect this datasets is to simplify importing process through URL. No need to create any API key like kaggle does. Also the reason I collected these datasets because these datasets contain thousands row of data, able of being used for analytic, and sometimes if I search in github or kaggle, it is hard to find relevant datasets with medium size.

I will update this repository regurally to add more datasets and remove duplicate / irrelevant dataset.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Import Dataset

You can access the datasets using methods below:

### Import by URL

#### 1. CSV file

This is how to import csv file that I usually used in jupyter notebook.

```sh
import pandas as pd

filename = 'Adidas_US_Sales.csv' # replace this only

url = 'https://github.com/azzindani/00_Data_Source/raw/main/'+ filename
df = pd.read_csv(url)
df.head()
```
You can add more arguments such as encoding, seperator, etc to read the dataset.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

#### 2. ZIP file

This is how to import zip file that I usually used in jupyter notebook.

* Starting by importing modules or packages
  ```sh
  from urllib.request import urlopen
  from io import BytesIO
  from zipfile import ZipFile
  
  filename = 'Diseases_And_Symptoms.zip' # replace this only
  
  url = 'https://github.com/azzindani/00_Data_Source/raw/main/'+ filename
  http_response = urlopen(url)
  zipfile = ZipFile(BytesIO(http_response.read()))
  zipfile.extractall()
  ```

* then i check file location in the folder
  ```sh
  os.listdir()
  ```

* for the example the file located in the first row of the list
  ```sh
  location = 0 # replace this only
  
  df = pd.read_csv(os.listdir()[location])
  df.head()
  ```
  
<p align="right">(<a href="#readme-top">back to top</a>)</p>

#### 3. JSON file

This is how to import json file that I usually used in jupyter notebook.

* regular json
  ```sh
  import pandas as pd
  
  filename = 'US_States.json' # replace this only
  
  url = 'https://github.com/azzindani/00_Data_Source/raw/main/'+ filename
  df = pd.read_json(url)
  df.head()
  ```
  
* nested  json
  ```sh
  import pandas as pd
  import json
  import requests
  
  filename = 'US_States.json' # replace this only
  
  url = 'https://github.com/azzindani/00_Data_Source/raw/main/'+ filename
  # Fetch the JSON content
  response = requests.get(url)
  data = response.json()
  # Normalize nested JSON data into a flat table
  df = pd.json_normalize(data)
  df.head()
  ```
  
<p align="right">(<a href="#readme-top">back to top</a>)</p>
  
#### 4. GEOJSON file

Geojson file contain the geographical landscape that defined in geometry coordinaes. This is how to import geojson file that I usually used in jupyter notebook.

```sh
import geopandas as gpd

filename = 'Indonesia_Cities.geojson' # replace this only

url = 'https://github.com/azzindani/00_Data_Source/raw/main/'+ filename
df = gpd.read_file(url)
df.head()
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>
  
### Installation

_Below is an example of how you can instruct your audience on installing and setting up your app. This template doesn't rely on any external dependencies or services._

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo
   ```sh
   git clone https://github.com/github_username/repo_name.git
   ```
3. Install NPM packages
   ```sh
   npm install
   ```
4. Enter your API in `config.js`
   ```js
   const API_KEY = 'ENTER YOUR API';
   ```
5. Change git remote url to avoid accidental pushes to base project
   ```sh
   git remote set-url origin github_username/repo_name
   git remote -v # confirm the changes
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage

Use this space to show useful examples of how a project can be used. Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish

See the [open issues](https://github.com/othneildrew/Best-README-Template/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Top contributors:

<a href="https://github.com/othneildrew/Best-README-Template/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=othneildrew/Best-README-Template" alt="contrib.rocks image" />
</a>

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

Use this space to list resources you find helpful and would like to give credit to. I've included a few of my favorites to kick things off!

* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Malven's Flexbox Cheatsheet](https://flexbox.malven.co/)
* [Malven's Grid Cheatsheet](https://grid.malven.co/)
* [Img Shields](https://shields.io)
* [GitHub Pages](https://pages.github.com)
* [Font Awesome](https://fontawesome.com)
* [React Icons](https://react-icons.github.io/react-icons/search)

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
[Next.js]: https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white
[Next-url]: https://nextjs.org/
[React.js]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[React-url]: https://reactjs.org/
[Vue.js]: https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D
[Vue-url]: https://vuejs.org/
[Angular.io]: https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white
[Angular-url]: https://angular.io/
[Svelte.dev]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[Svelte-url]: https://svelte.dev/
[Laravel.com]: https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white
[Laravel-url]: https://laravel.com
[Bootstrap.com]: https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white
[Bootstrap-url]: https://getbootstrap.com
[JQuery.com]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[JQuery-url]: https://jquery.com 
