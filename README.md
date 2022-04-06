# Ukraine and Russia Conflict Tweet IDs
 
The repository contains an ongoing collection of tweets IDs associated with the current conflict in Ukraine and Russia, which we commenced collecting on Februrary 22, 2022. We leveraged Twitter's search API to extract historical tweets, leading our dataset to contain tweets from February 17, 2022. These tweets are currently being processed and tweet IDs from Februrary 17 - 22 will be published in our next release. We leveraged Twitter’s streaming API to follow specified accounts and also collect in real-time tweets that mention specific keywords. To comply with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), we are only publicly releasing the Tweet IDs of the collected Tweets. The data is released for non-commercial research use. 

The associated paper to this repository will be updated shortly, once the paper is published on ArXiv.


## Data Organization
The Tweet-IDs are organized as follows:
* Tweet-ID files are stored in folders that indicate the year and month of the collection (YEAR-MONTH). 
* Individual Tweet-ID files contain a collection of Tweet IDs, and the file names all follow the same structure, with a prefix “ukraine_russia-” followed by the YEAR-MONTH-DATE-HOUR. 
* Note that Twitter returns Tweets in UTC, and thus all Tweet ID folders and file names are all in UTC as well. 

## Notes About the Data
### Other Notes
* We will keep a running summary of basic statistics as we upload data in each new release. 
* The file keywords.txt and accounts.txt contains the updated keywords and accounts respectively that we tracked in our data collection. Each keyword and account will be followed by the date we began tracking them, and date we removed them (if the keyword or account has been removed) from our tracking list. 
* Consider using tools such as the [Hydrator](https://github.com/DocNow/hydrator) and [Twarc](https://github.com/DocNow/twarc) to rehydrate the Tweet IDs. Instructions for both are in the next section. 
* Hydrating may take a while, and Tweets may have been deleted since our initial collection. If that is the case, unfortunately you will not be able to get the deleted Tweets from querying Twitter's API. 

## How to Hydrate

### Hydrating using [Hydrator](https://github.com/DocNow/hydrator) (GUI)
Navigate to the [Hydrator github repository](https://github.com/DocNow/hydrator) and follow the instructions for installation in their README. As there are a lot of separate Tweet ID files in this repository, it might be advisable to first merge files from timeframes of interest into a larger file before hydrating the Tweets through the GUI. 

### Hydrating using [Twarc](https://github.com/DocNow/twarc) (CLI)
Many thanks to Ed Summers ([edsu](https://github.com/edsu)) for writing this script that uses [Twarc](https://github.com/DocNow/twarc) to hydrate all Tweet-IDs stored in their corresponding folders. 

First install Twarc and tqdm
```
pip3 install twarc
pip3 install tqdm
```

Configure Twarc with your Twitter API tokens (note you must [apply](https://developer.twitter.com/en/apply-for-access) for a Twitter developer account first in order to obtain the needed tokens). You can also configure the API tokens in the script, if unable to configure through CLI. 
```
twarc configure
```

Run the script. The hydrated Tweets will be stored in the same folder as the Tweet-ID file, and is saved as a compressed jsonl file
```
python3 hydrate.py
```

# Data Usage Agreement / How to Cite
This dataset is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)). By using this dataset, you agree to abide by the stipulations in the license, remain in compliance with Twitter’s [Terms of Service](https://developer.twitter.com/en/developer-terms/agreement-and-policy), and cite the following manuscript: (link to paper will be updated once the paper has been published on ArXiv)


# Statistics Summary (v1.1)
Number of Tweets : **141,084,354**

Language breakdown of top 15 most prevalent languages :
| Language        | ISO     | No. tweets       | % total Tweets     |
|-------------    |-----    |------------      |----------------    |
| English         | en      | 103,148,176      | 73.11%             |
| Spanish         | es      | 6,824,764        | 4.84%              |
| French          | fr      | 5,322,756        | 3.77%              |
| Undefined       | und     | 4,742,414        | 3.36%              |
| Japanese        | ja      | 2,911,591        | 2.06%              |
| German          | de      | 2,873,438        | 2.04%              |
| Italian         | it      | 2,650,310        | 1.88%              |
| Russian         | ru      | 1,914,236        | 1.36%              |
| Turkish         | tr      | 1,668,966        | 1.18%              |
| Portuguese      | pt      | 1,518,027        | 1.08%              |
| Ukrainian       | uk      | 1,451,532        | 1.03%              |
| Polish          | pl      | 1,134,799        | 0.8%               |
| Thai            | th      | 715,638          | 0.51%              |
| Indonesian      | in      | 540,813          | 0.38%              |
| Dutch           | nl      | 437,723          | 0.31%              |

# Known Gaps
| Date          | Time              |
|-------------  |-----              |
|  | |


# Inquiries

Please read through the README and the closed issues to see if your question has already been addressed first. 

If you have technical questions about the data collection, please contact Emily Chen at **echen920[at]usc[dot]edu**.

If you have any further questions about this dataset please contact Dr. Emilio Ferrara at **emiliofe[at]usc[dot]edu**.

# Related Papers
