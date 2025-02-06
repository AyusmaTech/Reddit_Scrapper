# Reddit_Scrapper

# Scrape Your Favorite Reddit Content in Less Than 5 Minutes  

## Introduction  
Reddit is full of interesting discussions, advice, and personal stories, but finding and saving the content you care about can be time-consuming. This guide will walk you through building a simple Reddit scraper using Python. By following these steps, you’ll be able to extract posts from specific subreddits using an easy input method—all in under five minutes.  

### Estimated Time  
⏱ **5 minutes**  

### Skill Level  
🛠 **Beginner-Friendly**  

### Requirements  
✅ A Reddit account (for API access)  
✅ Python installed on your computer  
✅ Basic knowledge of running Python scripts  

---

## Step 1: Get Reddit API Credentials  
1. Go to [Reddit’s Developer Portal](https://www.reddit.com/prefs/apps).  
2. Click **Create an App** and fill in the required details:  
   - **Name:** Choose any name (e.g., "RedditScraper").  
   - **Type:** Select **Script**.  
   - **Redirect URI:** Use `http://localhost`.  
   - Save your **Client ID** and **Client Secret** from the app details.

     ![Python Script Setup](https://github.com/user-attachments/assets/007565e8-e339-4f48-aeb2-7a938f80ae6a)

---

## Step 2: Install Required Python Libraries  
Open a terminal or command prompt and run:  

```bash
pip install praw
```

This installs `praw`, the Python Reddit API wrapper.

---

## Step 3: Set Up Your Python Script  
Create a new Python file, e.g., `reddit_scraper.py`, and add the following code:  

```python
import praw

# Set up Reddit API authentication
client_id = "YOUR_CLIENT_ID"
client_secret = "YOUR_CLIENT_SECRET"
user_agent = "RedditScraper v1.0"

reddit = praw.Reddit(client_id=client_id, client_secret=client_secret, user_agent=user_agent)

def scrape_reddit(subreddit_name, post_limit=5):
    subreddit = reddit.subreddit(subreddit_name)
    print(f"Fetching top {post_limit} posts from r/{subreddit_name}...\n")
    
    for post in subreddit.hot(limit=post_limit):
        print(f"Title: {post.title}")
        print(f"Title: {post.selftext}")
        print(f"Upvotes: {post.score}")
        print(f"Link: {post.url}\n")

# Get user input for subreddit and post count
subreddit = input("Enter subreddit name: ")
num_posts = int(input("Enter number of posts to fetch: "))

scrape_reddit(subreddit, num_posts)
```


🔹 **Replace** `"YOUR_CLIENT_ID"` and `"YOUR_CLIENT_SECRET"` with your actual Reddit API credentials.

![Python Script Setup](https://github.com/user-attachments/assets/2a01760f-5ccc-4bdb-ab7b-bcfdc3827ee8)
---

## Step 4: Run the Script  
Save the file and run it in a terminal:  

```bash
python reddit_scraper.py
```

Enter a subreddit name (e.g., `relationships`) and the number of posts you want to scrape. The script will fetch and display posts in real-time.

![Terminal Output](https://github.com/user-attachments/assets/c192f6a1-51f6-4123-bd77-60afe4826cb2)
---

## Conclusion & Next Steps  
🎉 Congratulations! You’ve successfully built a Reddit scraper.  

🔹 **Enhancements to Try:**  
- Filtering posts based on keywords  
- Saving output to a file  
- Scraping comments along with posts  

Now, you can efficiently extract Reddit content in minutes. 🚀  

---
