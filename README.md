# U.S EDPA

<p>United States Economy Data Analysis Program</p>

## Description

### 개요
<ul> 
    <li>현재까지 기록된 미국의 여러 경제지표 데이터를 크롤링하고 다중 차트로 시각화한다.</li>
    <li>또한 Google Trends에서 특정 연도에 해당하는 상위 검색어를 추출해 워드 클라우드로 시각화한다.</li>
    <li>이러한 기능들을 활용해 경제지표 간의 상호 연관성과 경제 위기가 발생했을 때 경제지표가 어떻게 반응하는지 분석했다.</li>
</ul>

### Structure
![image](https://github.com/user-attachments/assets/ec16f079-b213-4996-b457-21df0cfcd42f)  

  
<b>Crawler</b>
    
![image](https://github.com/user-attachments/assets/57980013-9ead-45a0-820b-498250223845)
<ul>
    <li>Feds 결정금리, CPI 물가지수, 13 week T-bill 채권 수익률, S&P500 주가지수, Bitcoin, Gold 시세 총 6가지 경제지표를 데이터가 존재하는 가장 긴 기간만큼 크롤링하는 클래스를 작성했고 각각의 모듈로 만들었다.</li>
    <li>각 클래스는 crawl() 메서드를 가지며 해당 메서드는 각자가 가진 url을 크롤링해 dataFrame에 저장하고 csv파일을 생성한다. 크롤링한 데이터가 저장된 dataFrame을 반환한다.</li>
    <li>금리, 물가지수는 Investing.com 에서 Json파일을 크롤링했고, 이 외에 경제지표는 yahoo finance 웹사이트에서 Beatiful Soup 라이브러리를 이용해 크롤링하였다.</li>
</ul>
    
<b>Trends Crawler</b>
<ul>
    <li>Feds 결정금리가 급락했을 때 어떠한 사회적·경제적 이슈가 있었는지 보기위해 Google Trends 검색어를 가져오는 클래스이자 모듈이다.</li>
    <li>crawl() 메서드를 가지며 파라미터로 연도(year)를 받아 Google Trends에서 입력받은 연도의 상위 검색어 10개를 가져와 dataFrame을 만든다.</li>
    <li>검색어 10개를 워드클라우드 이미지로 만들어 시각화한다.</li>
</ul>
  
 <b>Main</b>
 <ul>
     <li>Jupyter notebook 형식의 파일로 Google colab에서 실행해야한다. clone github, install requirement, import Crawler module 하는 코드들이 선행된다. </li>
     <li>각 크롤러의 crawl 메서드를 실행해 각 경제지표들의 dataFrame을 만들고 비교 분석을 원하는 경제지표들을 차트로 시각화한다.</li>
     <li>차트로 시각화 하는 함수는 create_Chart() 함수로 dataFrames, titles를 담은 dictionary를 키워드인자로 받는다. 키워드 인자로 경제지표들의 데이터프레임을 받아 최소 1개, 최대 4개의 경제지표를 한 차트에 시각화가 가능하게 했다. </li>
     <li>차트 시각화는 plotly 라이브러리를 이용했다. plotly가  matplot 라이브러리보다 디자인이 예쁘고 cursor hover 시 데이터 정보를 볼 수 있어서 UX가 더 좋다고 느꼈다. </li>
 </ul>
 
 ## Getting Started

### Dependencies
<ol>
    <li>Execution Environment : Google Colab</li>
     <li>Language : Python</li>
    <li>Library
        <ol>
            <li>Crawling Data : Beautiful Soup, pytrends</li>
            <li>Data Visualizing : plotly, tqdm.notebook, wordcloud, cv2, google.colab.patches</li>
            <li>Google Trends : pytrends</li>
        </ol>
    </li>   
</ol>
<!--
* Describe any prerequisites, libraries, OS version, etc., needed before installing program.
* ex. Windows 10
-->

### Installing
<p>
    I already wrote codes in main.ipynp to install packages on requirements.txt and clone this repository. So you can just go next section : )
</p>
<!--
* How/where to download your program
* Any modifications needed to be made to files/folders
-->

### Executing program
<ol>
    <li>Go to this url to execute the main.ipynp file of this project :  
    <a href src="https://colab.research.google.com/github/catree42/U.S.EDAP/blob/main/main.ipynb">
        https://colab.research.google.com/github/catree42/U.S.EDAP/blob/main/main.ipynb 
    </a>
    </li>
    <li>
        Uncomment codes for cloning github, cd(chage directory), import TrendsCrawler.  
        I comment out these codes to execute the program on Pycharm but they need to be uncomment to be execute on Google colab.
    </li>
    <li>I hope you have fun with our program : )</li>
</ol>

<!--
* How to run the program
* Step-by-step bullets
```
code blocks for commands
```
-->

<!--
## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```
-->

## Authors

Giuk : 
Contributors names and contact info
김창회 :
김현승 :
송요섭 :


ex. Dominique Pizzie  
ex. [@DomPizzie](https://twitter.com/dompizzie)

<!--
## Version History

* 0.2
    * Various bug fixes and optimizations
    * See [commit change]() or See [release history]()
* 0.1
    * Initial Release

## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
-->

## Acknowledgments

Inspiration, code snippets, etc.
* [awesome-readme](https://github.com/matiassingers/awesome-readme)
* [PurpleBooth](https://gist.github.com/PurpleBooth/109311bb0361f32d87a2)
* [dbader](https://github.com/dbader/readme-template)
* [zenorocha](https://gist.github.com/zenorocha/4526327)
* [fvcproductions](https://gist.github.com/fvcproductions/1bfc2d4aecb01a834b46)
