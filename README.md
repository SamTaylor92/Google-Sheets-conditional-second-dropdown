# [Q2 2022] Google Sheets: Conditional second dropdown
<p align="right"> <a 
href="https://stackoverflow.com/users/18680621/sam-taylor" target="_blank"><img alt="StackOverflow" 
src="https://stackoverflow-badge.vercel.app/?userID=18680621" /></a> <a 
href="https://github.com/SamTaylor92" target="_blank"><img alt="Github" 
src="https://img.shields.io/badge/GitHub-181717.svg?style=for-the-badge&logo=GitHub&logoColor=white" /></a> <a 
href="https://www.linkedin.com/in/samjamest" target="_blank"><img alt="LinkedIn" 
src="https://img.shields.io/badge/LinkedIn-0A66C2.svg?style=for-the-badge&logo=LinkedIn&logoColor=white" /></a> <a 
href="https://signal.group/#CjQKIO50NLkjJmSisbgDD4OhRj5lHG7X-SJTOl-Dn8Fkc4FpEhCYdnCVL1ok4DlVNntY3mGe" target="_blank"><img alt="Signal" src="https://img.shields.io/badge/Signal-3A76F0.svg?style=for-the-badge&logo=Signal&logoColor=white"/></a> <a 
href="mailto:samtaylor92@live.co.uk" target="_blank"><img alt="Email" src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>
<p align="right">

## Project brief  
<p> <p align='center'> 
<img src="https://user-images.githubusercontent.com/105542266/173224954-e15a711c-1b16-43fc-9572-3c4ee6621c63.gif"/>
</p>
  
> **`Notes:`** 
> - For best results, use the [Google Drive](https://drive.google.com/drive/folders/13EqbSm3ax2uvTQEWrKaVIiDBAn2shNLL?usp=sharing) folder and view using [Google Sheets](https://docs.google.com/spreadsheets/d/1hobwIIgoEibHckIFwzYfgPot4w-5sN-vLuo0B402DNo/edit?usp=sharing) (as opposed to the GitHub repository)<br>
  
A small project for a client who wanted to save time when inputting data into a Google Sheet.<br>
<br> The aim was: 
- To allow two levels of dropdowns (data validation) where the second drop down was dependant on the first.
  
<h2> Tools</h2>
<p>
<a target="_blank"><img alt="Google Sheets" src="https://img.shields.io/badge/Google%20Sheets-34A853.svg?style=for-the-badge&logo=Google-Sheets&logoColor=white"/></a>
<a target="_blank"><img alt="Google Apps Script" src="https://img.shields.io/badge/Google%20Apps%20Script-7A1FA2.svg?style=for-the-badge&logo=Google&logoColor=white"/></a>
</p>

<details open>
<summary> <h2>Table of contents</h2></summary>	

- [Project brief](#project-brief)
- [Problem](#problem)
- [Desired outcome](#desired-outcome)
  - [Input data](#table-input-data)
  - [Categories for drop down menu](#table-categories-for-drop-down-menu)  
- [Solution](#solution)
- [Reference material](#reference-material)
  
</details>

<details open>
<summary> <h3>💼[Problem]</h3> </summary>
  
- The client had trouble with a procedure that required people to enter data into a [Google Sheet](https://docs.google.com/spreadsheets/d/1hobwIIgoEibHckIFwzYfgPot4w-5sN-vLuo0B402DNo/edit?usp=sharing).<br>
- Originally, people were copying and pasting information manually, which wasted time and caused input errors. <br>
- To solve this, the client requested 2 drop down menus to be created, where the second drop down changed what was displayed based on the first.  
<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	
  
</details>
</details>
  
  
<details open>
<summary> <h3>🎯[Desired outcome]</h3> </summary>
 
- The client wanted to optimize a procedure where a team of people categorised things in a [spreadsheet](https://docs.google.com/spreadsheets/d/1hobwIIgoEibHckIFwzYfgPot4w-5sN-vLuo0B402DNo/edit?usp=sharing), with the aim of reducing input errors and reducing input duration.
- There were two levels to the categorisation requested: a main level and a sub-level. 
- Depending on the main level chosen, the sub-level responses varied.
- The client also wanted to restrict the sub-level response choice to only those that fell under the corresponding main level.

`Example:`
> If category 1 was chosen, the sub-level drop-down menu should only display possible responses under category 1 <br>
  > ✅ `Main level:` Category 1 `Sub level:` 1A / 1B / 1C <br> 
  > ❌ `Main level:` Category 1 `Sub level:` 1A / 1B / 1C / 2A / 2B / 2C / 3A / 3B / 3C<br><br>

<p> <p align='center'> <img src="https://user-images.githubusercontent.com/105542266/173225603-19400870-8614-47d4-af3c-dccde4d31219.png"/> </p>  
<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	
  
<details open>
<summary> <h4>📊[Table: Input data]</h4> </summary>

| **DATE**                  | **EMAIL**       | **COMMENT** | **CATEGORY 1** | **CATEGORY 2** |
|---------------------------|-----------------|-------------|----------------|----------------|
| June 12, 2022  [10:25:04] | EMAIL1@test.com | -           | Category 1     | 1B             |
| June 12, 2022  [10:25:04] | EMAIL2@test.com | -           | Category 2     | 2C             |
| June 12, 2022  [10:25:04] | EMAIL3@test.com | -           |                |                |
| June 12, 2022  [10:25:04] | EMAIL4@test.com | -           |                |                |
| June 12, 2022  [10:25:04] | EMAIL5@test.com | -           |                |                |
| June 12, 2022  [10:25:04] | EMAIL6@test.com | -           |

<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	  
  
</details>

<details open>
<summary> <h4>📊[Table: Categories for drop down menu]</h4> </summary>  

| **Category 1** | **Category 2** | **Category 3** | **Category 4** |
|----------------|----------------|----------------|----------------|
| 1A             | 2A             | 3A             | 4A             |
| 1B             | 2B             | 3B             | 4B             |
| 1C             | 2C             | 3C             | 4C             |
|                | 2D             | 3D             | 4D             |
|                | 2F             |                | 4E             |
|                | 2G             |
<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	
  
</details>
  
  
</details>
</details>  

<details open>
<summary> <h3>💡[Solution]</h3> </summary>

For best results, use the [Google Drive](https://drive.google.com/drive/folders/13EqbSm3ax2uvTQEWrKaVIiDBAn2shNLL?usp=sharing) folder and view using [Google Sheets](https://docs.google.com/spreadsheets/d/1hobwIIgoEibHckIFwzYfgPot4w-5sN-vLuo0B402DNo/edit?usp=sharing).<br>  
`Google Drive:` [(Link)](https://drive.google.com/drive/folders/13EqbSm3ax2uvTQEWrKaVIiDBAn2shNLL?usp=sharing)  
`Repository:` [(Link)](https://github.com/SamTaylor92/Google-Sheets-conditional-second-dropdown)<br> 
`Formula:` 
```
function onEdit(){

  var ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var datass = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Dependant")
  
  var activeCell = ss.getActiveCell();
  
  if(activeCell.getSheet().getSheetName() == "Input" && activeCell.getColumn() == 4 && activeCell.getRow() > 1){
  
    if(activeCell.getValue() === ""){
      SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Input").getRange(activeCell.getRow(),5).clearContent();
      SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Input").getRange(activeCell.getRow(),5).clearDataValidations();
      }
    activeCell.offset(0, 1).clearContent().clearDataValidations();

      var makes = datass.getRange(1, 1, 1, datass.getLastColumn()).getValues();
  
      var makeIndex = makes[0].indexOf(activeCell.getValue()) + 1;
      
        if(makeIndex != 0) {
  
      var validationRange = datass.getRange(2, makeIndex, datass.getLastRow());
      var validationRule = SpreadsheetApp.newDataValidation().requireValueInRange(validationRange).setAllowInvalid(false).build();
      activeCell.offset(0, 1).setDataValidation(validationRule);
  
  }
  
}
}
```    
<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	

</details>
</details>

<details open>
<summary> <h3>📚[Reference material]</h3> </summary>
  
- [x] [Youtube tutorial 1](https://www.youtube.com/watch?v=8aOn0VMgG1w)
- [x] [Youtube tutorial 2](https://www.youtube.com/watch?v=s-I8Z4nTDak)    
- [x] [Table Convert](https://tableconvert.com/)
<p align='right'><a href="#-tools" target="_blank">⬆</a></p>	
  
</details>
</details>

</p>

</br></br>
© 2022 GitHub, Inc.
Terms
Privacy
