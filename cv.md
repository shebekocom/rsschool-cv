# Nikolay Shebeko

**Nizhny Novgorod, Russia**  
**Telephone number:** [+7(915)955-87-77](tel:+79159558777)  
**E-mail:** [nikolay.shebeko@gmail.com](mailto:nikolay.shebeko@gmail.com)  
**Github:** [https://github.com/shebekocom](https://github.com/shebekocom)  

## About me:  
For 10 years I have been making money in the network business, promoting health products and motivating people to make money through direct sales. I always dreamed of being a developer and creating digital products. So I decided to remember my dream and make it a goal. I already know html and css, do website design on Tilda. My goal is to learn javascript and start using reactjs. My main goal is to increase my income by doing what I love.

## Technical skills:  
- HTML/HTML5
- CSS/CSS3
- Bootstrap 3/4
- Java Script
- experience in: BEM, jQuery, React
- Tools: Git, VS Code, Adobe Photoshop, Figma

```javascript
const searchForm = document.querySelector('#search-form');
const movie = document.querySelector('#movies');
const urlPoster = 'https://image.tmdb.org/t/p/w500';

function apiSearch(event) {
    event.preventDefault();
    const searchText = document.querySelector('.form-control').value;
    if (searchText.trim().length === 0) {
        movie.innerHTML = '<h2 class="col-12 text-center text-danger">Поле поиска не должно быть пустым</h2>';
        return
    }

    movie.innerHTML = '<div class="spinner"></div>';

    fetch('https://api.themoviedb.org/3/search/multi?api_key=942cf276adefa306549de647ce5a6e18&language=ru&query=' + searchText)
        .then(function (value) {
            if (value.status !== 200) {
                return Promise.reject(new Error(value.status));
            }
            return value.json();
        })
        .then(function (output) {
            let inner = '';
            if (output.results.length === 0) {
                inner = '<h2 class="col-12 text-center text-info">По вашему запросу ничего не найдено</h2>';
            }
            output.results.forEach(function (item) {
                let nameItem = item.name || item.title;
                let dateItem = item.first_air_date || item.release_date;
                const poster = item.poster_path ? urlPoster + item.poster_path : './img/noposter.png';
                let dataInfo = '';
                if (item.media_type !== 'person') dataInfo = `data-id="${item.id}" data-type="${item.media_type}"`;
                inner += `
                 <div class="col-12 col-md-6 col-xl-3 item">
                 <img src="${poster}" class="img_poster" alt="${nameItem}" ${dataInfo}>
                 <p>${nameItem}</p>
                    <div class="alert alert-primary" role="alert">
                    Дата релиза: </br>${dateItem}
                    </div>
                 </div>`;
            });
            movie.innerHTML = inner;

            addEventMedia();

        })
        .catch(function (reason) {
            movie.innerHTML = 'Упс, что то пошо не так!';
            console.error('error: ' + reason);
        });

}

searchForm.addEventListener('submit', apiSearch);
```
## Experience:  
- CodeAcademy profile [@nshebeko](https://www.codecademy.com/nshebeko)  
- HTML Academy profile [@nshebeko](https://htmlacademy.ru/profile/nshebeko)

## Education:
Graduated Lobachevsky State University of Nizhny Novgorod in 2007 faculty of Applied Informatics.

## English:
I studied English at school and university. At the courses in Skyeng they put me on level A1 Elementary.