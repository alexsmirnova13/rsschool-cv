![Smirnova A.](https://avatars.githubusercontent.com/u/100535240?v=4)

# Smirnova Aleksandra

## Contacts

- Telegram | @Alexrusty13
- Discord | Yadviga#8124
- [LinkedIn](https://www.linkedin.com/in/asmirnova131194/)

## Summary

I am studying in RS-School. Want to be a real JS programmer.

## Skills

- English B1/B2
- JS
- TS
- NodeJs
- HTML
- CSS
- React
- Python

## My code

This is the part of my previous project named [Pokedex](https://alexsmirnova13.github.io/allPokemons/)
I downloaded information for Pokedex from API. There was three options. Preload for preloading all pokemons, download one pokemon by ID and downloading all pokemons.

    import OnePokeStandart from '../models/OnePokeStandart';
    import axios from 'axios';

    export default class CardService {
        static async getAll(limit = 24, page = 1) {
            const response = await axios.get('https://pokeapi.co/api/v2/pokemon', {
                params: {
                    limit,
                    offset: (page - 1) * limit,
                },
            });
            const {count, results} = response.data;
            const fullyLoaded = await Promise.all(results.map(async u => axios.get(u.url).then(resp => resp.data)));
            const abstractedFullyLoaded = fullyLoaded.map(u => new OnePokeStandart(u));

            return [abstractedFullyLoaded, count];
        }

        static async getById(id) {
            const response = await axios.get(`https://pokeapi.co/api/v2/pokemon/${id}`);
            return response;
        }

        static async preload(count) {
            const response = await axios.get('https://pokeapi.co/api/v2/pokemon', {
                params: {
                    limit: count,
                },
            });
            return response;
        }
    }

## Experience

I have only home-experience of working JS-programmer. You could saw example of my code and link on my project above.

## Education

- SPb SUAI 2012-2016 Bachelor's degree "Transport logistic"
- SPb SUAI 2016-2018 Master's degree "Transport logistic"
- Internet training from EPAM-video Course
- RS-School
- [LearnJS](https://learn.javascript.ru/)

## Not native languages

- English B1/B2. Practice with non russian speaking teacher in Skyeng. A lot of video games with non russian speaking teammates.
- French A1. Studying by myself in Duolingo.
- Turkish A1. Studying by myself in Duolingo. And trying to talk to people in the street :D