# Dictionary-App
This document provides an overview of the `MainActivity` class, , which is the main file of the Java Dictionary app. It describes the purpose of the class and provides an explanation of its structure and functionality.

## Class Overview
The `MainActivity` class is an `AppCompatActivity` subclass that serves as the entry point and main activity of the Java Dictionary app. It handles user interactions, displays search results, and manages the UI components.

## Class Structure
The `MainActivity` class consists of the following elements:

### Fields
- `search_view`: A SearchView instance for entering search queries.
- `textView_word`: A TextView instance for displaying the word.
- `recycler_phonetics`: A RecyclerView instance for displaying phonetic data.
- `recycler_meanings`: A RecyclerView instance for displaying meaning data.
- `progressDialog`: A ProgressDialog instance for showing loading progress.
- `phoneticsAdapter`: A PhoneticsAdapter instance for managing phonetics data in the recycler_phonetics.
- `meaningAdapter`: A MeaningAdapter instance for managing meaning data in the recycler_meanings.
### Methods
- `onCreate()`: This method is called when the activity is created. It initializes the UI components, sets up event listeners, and initiates a word meaning request.
- `listener`: An OnFetchDataListener implementation for handling the response from the word meaning request.
- `showData(APIResponse apiResponse)`: A method that displays the retrieved word meaning data in the UI.

## Functionality
The `MainActivity` class provides the following functionality:

1. Initializes UI components: The `onCreate()` method initializes the search_view, textView_word, recycler_phonetics, recycler_meanings, and progressDialog components by finding them in the layout XML file.
2. Initiates a word meaning request: The `onCreate()` method creates a RequestManager instance and calls its `getWordMeaning()` method to fetch the meaning of the word "hello". It also sets up the listener to handle the response.
3. Handles search events: The search_view is set up with an `OnQueryTextListener` to handle text submission events. When a query is submitted, the `getWordMeaning()` method is called to fetch the meaning of the entered query. The progress dialog is shown during the request.
4. Displays word meaning data: The `showData(APIResponse apiResponse)` method is responsible for updating the UI with the retrieved word meaning data. It sets the textView_word with the word, sets up the phoneticsAdapter and meaningAdapter with the respective data, and attaches them to their respective RecyclerView components.

## Usage
To use the `MainActivity` class, follow these steps:

1. Ensure that the necessary dependencies, such as the SearchView, RecyclerView, and adapter classes, are included in the project.
2. Create a new instance of the `MainActivity` class and set it as the main activity in the AndroidManifest.xml file.
3. Implement the `OnFetchDataListener` interface to handle the response from the word meaning request.
4. Customize the UI layout by modifying the activity_main.xml file.
5. Run the app and enter a search query in the search_view to fetch and display the word meaning.
