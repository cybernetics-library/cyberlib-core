# Cybernetics Library Core

## Setup

### Install

```pip install -r requirements.txt```

### API

`python app.py`.

When running for production, this is run using gunicorn and a virtualenv with pm2 using the shell script `start_library_api.sh`.

Endpoints:

- `/plot/link` [POST]: Link a plot to a book. Needs `book_id`, `plot_id`, `station_id`, `timestamp`.
- `/plot/unlink` [POST]: Unlink a plot and a book. Needs `book_id`, `plot_id`, `station_id`, `timestamp`.
- `/plot/rename` [POST]: Rename a plot. Needs `book_id`, `plot_id`, `station_id`, `timestamp`.
- `/plot/names` [GET]: Return all the names of the plots
- `/plots` [GET]: Return all of the plots and their names and links
- `/plots/<plotid>` [GET]: Return only one of the plots and their names and links
- `/books` [GET]: Return all of the books and their names and links
- `/books/<bookid>` [GET]: Return only one of the books and their names and links




### Visualizations 

In the `viz/` directory:
```
npm install -d
npm start
```

Then visit `localhost:8081/planet`, etc.

## Architecture

`viz/` directory holds all the node & THREE.js visualizations. 

`app/` directory holds the server-side API with endpoints. Global API is `https://library.cybernetics.social`. Much of the logic can happen in here.

