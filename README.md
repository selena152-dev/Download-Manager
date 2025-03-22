# Download Manager

A simple, yet efficient, file download manager built using **JavaFX** and **Java**. This application allows users to download multiple files concurrently, with support for pausing, resuming, and canceling downloads. It also includes a real-time progress tracker and the ability to delete completed or paused downloads.

## Features

- **Multiple File Downloads**: Supports downloading multiple files concurrently in the background.
- **Progress Tracking**: Real-time progress updates for each download displayed in a user-friendly table view.
- **Pause/Resume Downloads**: Users can pause and resume downloads as needed, with the state reflected in the UI.
- **Delete Files**: Delete selected downloads from the list of active downloads.
- **Scheduled Progress Updates**: The download progress is periodically updated without blocking the main UI thread.
- **Thread Pool Management**: Efficient management of download threads using Java's `ExecutorService` to handle multiple concurrent downloads.

## Technologies Used

- **Java** (version 8 or above)
- **JavaFX** for building the graphical user interface (GUI)
- **ExecutorService** for concurrent downloading
- **ScheduledExecutorService** for periodic progress updates
- **CompletableFuture** for managing asynchronous downloads and handling errors gracefully
- **AtomicBoolean** for managing pause/resume logic in a thread-safe manner

## Usage

Once the application is running:

1. Add files to the download queue by entering their URL and file name in the provided input fields.
2. The progress of each download will be displayed in the TableView, showing the file name, URL, size, download state (e.g., Paused, Processing), and download progress.
3. Users can interact with the following buttons:
   - **Pause**: Pauses the selected download(s).
   - **Resume**: Resumes the paused download(s).
   - **Delete**: Removes the selected download(s) from the queue.
   - **Pause All**: Pauses all ongoing downloads.
   - **Resume All**: Resumes all paused downloads.
   - **Delete All**: Removes all downloads from the queue.

## How It Works

- **File Downloading**: Files are downloaded asynchronously in the background using a fixed thread pool. Each download's progress is updated periodically.
- **Pause and Resume**: The user can pause and resume downloads, and the application's state will be reflected in the UI. The pause functionality uses a shared AtomicBoolean flag to control thread execution.
- **UI Updates**: The application uses JavaFX's TableView to display the status of downloads, updating the progress bar and other information in real-time on the main UI thread using `Platform.runLater()`.

## Future Improvements

- **Error Handling**: More robust error handling and retries for failed downloads.
- **Resume on Restart**: Implement the ability to resume downloads even after closing and reopening the application.
- **File Management**: Enhance file management features (e.g., viewing download folder, file renaming).
- **Download Speed Tracking**: Display download speed for each file.
