Yo yo, breakdown of what each code does is below so you know, I have done them in the order you'll need to run each code for. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**BOT THAT MAKES THE FOLDERS FOR YOU**

It imports the os module, which provides a way to interact with the operating system.

The variable model_name is set to whatever you want. This will be used as the name for the main folder.

The variable base_directory is set to "C:\Example\Reddit Bots\Models". This is the base directory where the folder structure will be created.

The variable model_folder is created by joining the base_directory and model_name using the os.path.join() function. This will be the main folder that will contain the subfolders.

The os.makedirs() function is used to create the model_folder. The exist_ok=True argument ensures that the folder is created only if it doesn't already exist.

Two additional folders are created within the model_folder:

populated_subreddits_folder1: This is a subfolder named "Populated Subreddits - Account 1".
populated_subreddits_folder2: This is a subfolder named "Populated Subreddits - Account 2".

Both subfolders are created using os.makedirs() with exist_ok=True to ensure they are created only if they don't already exist.

The variable model_photos_folder is created by joining the model_folder and "Model Photos" using os.path.join(). This is a subfolder within the model_folder where the "Bum", "Boobs", and "All" subfolders will be created.

The model_photos_folder is created using os.makedirs() with exist_ok=True.

A loop is used to create three subfolders within the model_photos_folder: "Bum", "Boobs", and "All". These subfolders are created using os.makedirs() with exist_ok=True.

For each subfolder, a text file is created with the same name as the subfolder but capitalized. The text file is created using open() with the mode 'a' (append), and then immediately closed using .close().

Finally, a message "Folder structure created successfully!" is printed to indicate that the folder structure has been created.

The code creates a folder structure based on the model_name variable, with subfolders for populated subreddits and model photos, as well as additional subfolders and text files within the model photos folder.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**BOT THAT DISTRIBUTES THE PHOTOS FOR YOU**

It prompts the user to enter various criteria such as the model's name, the account to populate, desired subreddits, hair color, age, body type, height, tattoos, piercings, ethnicity, and whether the model has had work done.

Based on the entered criteria, it determines the source directory (src_dir) where the model's photos are located and the destination directory (dst_dir) where the photos will be copied.

It initializes a list called excluded_subreddits to store the subreddits that will be excluded based on the specified criteria.

Depending on the account specified, it adds specific subreddits to the excluded_subreddits list.

If the desired subreddits are "of101" or "all," it adds additional subreddits to the excluded_subreddits list.

It adds subreddits to the excluded_subreddits list based on the model's hair color.

It adds subreddits to the excluded_subreddits list based on the model's age.

It adds subreddits to the excluded_subreddits list based on the model's body type.

It adds subreddits to the excluded_subreddits list based on the model's height.

It adds subreddits to the excluded_subreddits list based on whether the model has tattoos or piercings.

It adds subreddits to the excluded_subreddits list based on the model's ethnicity.

It adds subreddits to the excluded_subreddits list based on whether the model has had work done.

The script defines a file_mapping dictionary that maps a destination file name (e.g., "All.txt") to a list of subreddits.

Finally, the script copies the model's photos from the source directory (src_dir) to the destination directory (dst_dir) while excluding the subreddits listed in the excluded_subreddits list.

Overall, the code is used to organize and populate folders or text files with photos and links based on various criteria and subreddit selections.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**BOT THAT DELETES FOLDERS**

It imports the necessary modules: glob for file matching, and os for file and directory operations.

It sets the value of the variable modelname to "modelname". This represents the name of the model.

It constructs the dir_path variable by joining the path components using os.path.join(). This specifies the directory path where the folders to be cleared are located.

It uses glob.glob() to retrieve a list of folders in the specified directory (dir_path).

It counts the number of folders found and stores it in the num_folders_to_clear variable.

It initializes the variables num_folders_processed and num_files_processed to keep track of the number of folders and files processed.

It prints the number of folders found.

It prompts the user to input whether they want to clear all folders by asking for a "yes" or "no" response. The input is converted to lowercase using lower().

If the user input is "yes", it proceeds with clearing all the folders:

a. It iterates over each folder path in the folders_to_clear list.

b. Inside the loop, it uses glob.glob() to retrieve a list of files in the current folder.

c. It iterates over each file path in the files_to_clear list.

d. If the current path represents a file (checked with os.path.isfile()), it removes the file using os.remove() and increments the num_files_processed variable.

e. It increments the num_folders_processed variable.

f. If any exception occurs during the process, it prints an error message indicating the folder path and the encountered exception.

g. After processing all folders, it prints the number of folders and files processed.

If the user input is anything other than "yes", it simply prints "No folders were cleared."

The code is designed to clear the contents of folders within a specified directory. If the user confirms that they want to clear all folders, it iterates over each folder, removes all files within the folder, and provides a summary of the number of folders and files processed.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**WRITES CODE FOR YOU**

It imports necessary modules: os, datetime, and random.

It defines the onlyfans_links dictionary, mapping model names to corresponding OnlyFans links.

It defines the directories list, containing dictionaries with directory paths and output file names.

It defines the subreddit_flair_ids dictionary, mapping subreddit names to their corresponding flair IDs.

It defines the subreddit_OF_link dictionary, mapping subreddit names to their corresponding OnlyFans links.

It prompts the user to enter the model's name.

It creates a save_directory path based on the model name and checks if it exists. If not, it creates the directory.

It iterates over the directories list and performs the following steps for each directory:

a. It retrieves the directory path and output file name.

b. It creates the save_file_path by joining the save_directory and output_file.

c. It opens the save_file_path in write mode.

d. It obtains a list of folder names within the directory and shuffles them randomly.

e. It iterates over the folder names and performs the following steps for each folder:

It retrieves the subreddit name by removing the first two characters from the folder name and converting it to lowercase.

It generates a random number of minutes for the delay.

It retrieves the flair ID and OnlyFans link associated with the subreddit name.

It sets the paths for the posted links and titles directories.

It writes a code block to the output file, which includes the subreddit name, delay, and various file paths.

The code block written to the output file appears to involve functions related to Reddit integration and posting. However, the implementation of these functions is not provided in the code snippet.

The code ends after the loop completes for all directories.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**SCRAPES TITLES FOR THE POSTS**

It imports the necessary modules: praw for Reddit API access and os for file operations.

It creates a praw.Reddit instance by providing the client ID, client secret, and user agent.

It prompts the user to enter the model's name and age.

It constructs the file_path and directory_path variables based on the model's name and age.

It creates the directory specified by directory_path if it doesn't exist.

It combines the directory path with the model name to form the file_path for saving the titles.

It initializes the subreddit variable with the subreddit name 'onlyfansgirls101'.

It retrieves the latest 200 posts from the subreddit using subreddit.new(limit=200).

It sets a counter variable num_posts_written to keep track of the number of posts written.

It opens the file_path in write mode and starts a loop to process each post.

For each post, it retrieves the title.

It checks if the title contains any of the specified keywords or digits. If it does, the loop continues to the next post.

It writes the formatted title to the file, including the age and the title itself.

It increments the num_posts_written counter.

If num_posts_written reaches 200, it breaks the loop.

Once the loop finishes, it prints "Done" to indicate completion.

This code essentially scrapes titles from the specified subreddit, filters out posts with unwanted keywords or digits in the title, and saves the remaining titles along with the associated age to a file.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**THE ACTUAL POST BOT**

It imports the required modules: praw, random, os, datetime, and time.

It defines a global variable reddit_con_count and initializes it to 0. This variable is used to keep track of the number of times the Reddit connection is made.

The redditConnect function is defined, which establishes a connection to Reddit using the provided credentials (client ID, client secret, user agent, username, and password). It increments the reddit_con_count variable and returns the Reddit instance.

The get_files_from_folder function takes a folder path as input and returns a list of files present in that folder.

The get_links_from_file function takes a file path as input, reads the file, and returns a list of links present in the file.

The postToReddit function is the main function responsible for posting content to a specified subreddit. It takes several parameters: redditCon (the Reddit instance), subreddit (the name of the subreddit to post to), title_file_path (the path to a file containing titles), image_folder_path (the path to a folder containing image files), video_link_file_path (the path to a file containing video links), onlyfans_link (an OnlyFans link), posted_titles_file_path (the path to a file storing previously posted titles), posted_links_file_path (the path to a file storing previously posted links), and flair_id (the flair ID for the post).

The function reads the titles from the title file and checks if any titles have already been posted. It keeps track of posted titles and links in separate files.

It selects an available title randomly from the list of available titles.

It gets the list of image files from the image folder and filters out the ones that have already been posted.

It gets the available links from the video link file and filters out the ones that have already been posted.

If there are no available titles, images, or links, the function prints an appropriate message and returns.

If there are available images and either no available links or a random choice between available images and links, it selects an image randomly, writes the image file name to the posted links file, and submits the image with the selected title to the subreddit.

If there are available links, it selects a link randomly, writes the link to the posted links file, and submits the link with the selected title to the subreddit.

It writes the selected title to the posted titles file.

After a delay of 4 seconds, if the onlyfans_link parameter is provided, it posts a comment on the submitted post with the provided OnlyFans link.

The main part of the code executes the redditConnect function to establish a Reddit connection.

It then waits for a specific time using time.sleep before calling the postToReddit function multiple times with different parameters to post to different subreddits.

Overall, this script seems to automate the process of posting content (images or links) to multiple subreddits on Reddit, using specific files for titles, images, and links.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**IF NEEDED - FLAIR ID BOT**

The redditConnect() function establishes a connection to the Reddit API by creating a praw.Reddit instance. It requires client ID, client secret, user agent, username, and password to authenticate with Reddit. These credentials are provided in the function.

After connecting to Reddit, the function prints whether the connection is read-only or not.

The function returns the reddit instance, allowing it to be used for further Reddit API operations.

The reddit instance is created by calling redditConnect(), which establishes the connection to Reddit.

The code specifies the subreddit name as 'WhiteCheeks'. You can change this to the desired subreddit you want to work with.

The for loop iterates over the link_templates attribute of the subreddit's flair. This attribute contains a list of dictionaries, where each dictionary represents a flair template.

Within the loop, it prints the flair text and flair ID for each flair template. The format of the output string is "Flair text: {flair text}, Flair ID: {flair ID}".

The code is useful for retrieving the flair templates of a subreddit and obtaining their associated text and ID. Flair templates are predefined sets of flairs that users can choose when posting or commenting in a subreddit. By printing the flair text and ID, you can understand the available flairs in the subreddit and use this information for various purposes, such as analyzing user engagement, organizing content, or creating customized bot interactions based on specific flairs.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
