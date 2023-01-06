# prompt_gen

A python package for automating your Prompt Engineering workflows - [https://github.com/Just-Understanding-Data-Ltd/promp_gen](https://github.com/Just-Understanding-Data-Ltd/promp_gen). This package helps you to get started with creating text to image prompts.

There are several properties and methods that you can use to create prompts. Data has been populated using GPT and curating datasets.

## ⌛️ Installation

```bash
pip install prompt-gen
```

## 🎛 API

### <kbd>class</kbd> `PromptGenerator`

#### <kbd>method</kbd> `PromptGenerator.__init__`

An instance of `PromptGenerator`, initialized with the default config. Useful as a quick
shortcut if you don't need to customize initialization.

```python
from prompt_gen import PromptGenerator
prompt_model = PromptGenerator()
```

| Argument       | Type        | Description                                                                                              | Default |
| -------------- | ----------- | -------------------------------------------------------------------------------------------------------- | ------- |
| `styles`       | `List[str]` | Styles such as `['fauvism', 'cubism', 'abstract']`                                                       | `None`  |
| `perspectives` | `List[str]` | Perspectives about the image prompt such as the angle which the shot has been taken in `['from behind']` | `None`  |
| `vibes`        | `List[str]` | Vibes are a way to add a look/theme to your image prompts.                                               | `None`  |
| `boosters`     | `List[str]` | Boosters are an alternative way to add a look/theme to your image prompts.                               | `None`  |
| `formats`      | `List[str]` | Formats include `['oil painting'`, `'photo-realistic'`, `'cartoon drawing]'` etc                         | `None`  |
| `characters`   | `List[str]` | Characters such as `['Mickey Mouse', 'Donald Duck']`                                                     | `None`  |
| `scenarios`    | `List[str]` | Actions that your characters are taking such as `['Rowing', 'Swimming', 'Eating some food']`             | `None`  |
| `locations`    | `List[str]` | A list of locations such as `['New York', 'Big Ben']`                                                    | `None`  |
| **RETURNS**    | `Printer`   | The initialized PromptGenerator.                                                                         | -       |

If you don't include any of the arguments above, then defaults will be included within your image prompts.

---

&nbsp;

### <kbd>properties</kbd>

```python
from prompt_gen import PromptGenerator
prompt_model = PromptGenerator()
prompt_model.styles # Returns a list of styles
prompt_model.perspectives # Returns a list of perspectives
prompt_model.vibes # Returns a list of vibes
prompt_model.boosters # Returns a list of boosters
prompt_model.formats # Returns a list of formats
prompt_model.characters # Returns a list of characters
prompt_model.scenarios # Returns a list of scenarios
prompt_model.locations # Returns a list of locations
```

---

&nbsp;

#### <kbd>method</kbd> `PromptGenerator.generate_single_prompt`

```python
prompt_model = PromptGenerator()
prompt = prompt_model.generate_single_prompt()
print(f"This is a single prompt: {prompt}")
```

```python
prompt_model = PromptGenerator()
prompt = prompt_model.generate_single_prompt(use_vibe=True)
print(f"This is a single prompt: {prompt}")
```

| Argument          | Type   | Description                                                                                               | Default |
| ----------------- | ------ | --------------------------------------------------------------------------------------------------------- | ------- |
| `style`           | `str`  | Styles such as fauvism, cubism or abstract                                                                | `None`  |
| `perspective`     | `str`  | Perspectives about the image prompt such as the angle which the shot has been taken in `['from behind']`. | `None`  |
| `vibe`            | `str`  | Vibes are a way to add a look/theme to your image prompts.                                                | `None`  |
| `booster`         | `str`  | Boosters are an alternative way to add a look/theme to your image prompts.                                | `None`  |
| `format`          | `str`  | Formats include `['oil painting'`, `'photo-realistic'`, `'cartoon drawing]'` etc.                         | `None`  |
| `character`       | `str`  | Characters such as `['Mickey Mouse', 'Donald Duck']`                                                      | `None`  |
| `scenario`        | `str`  | Actions that your characters are taking such as `['Rowing', 'Swimming', 'Eating some food']`              | `None`  |
| `location`        | `str`  | A list of locations such as `['New York', 'Big Ben']`                                                     | `None`  |
| `use_vibe`        | `bool` | A boolean to opt into adding a vibe to your image prompt. Defaults to False.                              | `False` |
| `use_perspective` | `bool` | A boolean to opt into adding a perspective to your image prompt. Defaults to False.                       | `False` |
| `use_booster`     | `bool` | A boolean to opt into adding a booster to your image prompt. Defaults to False.                           | `False` |
| **RETURNS**       | `str`  | Returns a single generated text prompt.                                                                   | -       |

---

&nbsp;

#### <kbd>method</kbd> `PromptGenerator.generate_random_prompts`

```python
prompt_model = PromptGenerator()
prompts = prompt_model.generate_random_prompts(number_of_prompts=10)
print(f"This is a list of random prompts: {prompts}")

['Sauron, the dark lord playing video games in tikal in the format of a pixel art in a ancient egyptian art style',
 '"beauty and the beast" (belle) playing an instrument or singing in palace of versailles in the format of a political cartoon from u.s. newspaper in a art deco style',
 'Austin powers boating in eiffel tower in the format of a illustration in a impressionist style',
 'Fleur delacour hiking in skara brae in the format of a studio photography in a game of thrones style',
 'Fleur delacour playing an instrument or singing in kinkaku-ji in the format of a professional corporate portrait in a renaissance style',
 'Legolas greenleaf shopping in the leaning tower of pisa in the format of a one-line drawing in a fauvism style',
 'Max goof going to a bar or club in the great wall of china in the format of a roman mosaic in a steampunk style',
 'James bond reading books or comics in giza necropolis in the format of a book cover in a realism style',
 'Percy weasley visiting a zoo or aquarium in giza necropolis in the format of a watercolor painting in a hudson river school style',
 'Cedric diggory taking a walk in uluru in the format of a album art cover in a 1990s disney, cel shading style']
```

```python
prompt_model = PromptGenerator()
prompts = prompt_model.generate_random_prompts(number_of_prompts=30, characters=['Donald Duck'], use_vibe=True)
print(f"This is a list of random prompts: {prompts}")
```

| Argument          | Type        | Description                                                                                               | Default |
| ----------------- | ----------- | --------------------------------------------------------------------------------------------------------- | ------- |
| `styles`          | `List[str]` | Styles such as `['fauvism', 'cubism']`                                                                    | `None`  |
| `perspectives`    | `List[str]` | Perspectives about the image prompt such as the angle which the shot has been taken in `['from behind']`. | `None`  |
| `vibes`           | `List[str]` | Vibes are a way to add a look/theme to your image prompts.                                                | `None`  |
| `boosters`        | `List[str]` | Boosters are an alternative way to add a look/theme to your image prompts.                                | `None`  |
| `formats`         | `List[str]` | Formats include `['oil painting'`, `'photo-realistic'`, `'cartoon drawing]'` etc.                         | `None`  |
| `characters`      | `List[str]` | Characters such as `['Mickey Mouse', 'Donald Duck']`                                                      | `None`  |
| `scenarios`       | `List[str]` | Actions that your characters are taking such as `['Rowing', 'Swimming', 'Eating some food']`              | `None`  |
| `locations`       | `List[str]` | A list of locations such as `['New York', 'Big Ben']`                                                     | `None`  |
| `use_vibe`        | `bool`      | A boolean to opt into adding a vibe for all your image prompts. Defaults to False.                        | `False` |
| `use_perspective` | `bool`      | A boolean to opt into adding a perspectivefor all your image prompts. Defaults to False.                  | `False` |
| `use_booster`     | `bool`      | A boolean to opt into adding a booster for all your image prompts. Defaults to False.                     | `False` |
| **RETURNS**       | `List[str]` | Returns a list of randomly generated prompts.                                                             | -       |

---

&nbsp;

# What makes part of a good prompt for AI?

## Locations:

- Cities
- Made up environments
- Important landmarks

---

## Characters:

- Animals
- Characters from Films (Star Wars, The Matrix)
- Characters from TV Shows (Friends, The Simpsons)
- Characters from Books (Harry Potter, The Lord of the Rings)
- Characters from Comics (Star Wars, The Matrix)

---

## Styles:

These include for example `abstract` or `cartoon` etc.

---

## Perspectives:

These include for example `from behind`, `from above`, `from the side` etc.

---

## Vibes/Boosters act as a style:

Vibes/Boosters are a different way to describe the style.

---

&nbsp;

## Additional Resources:

- [A visual prompt editing tool](https://tools.saxifrage.xyz/prompt)
- Prompt Generator: https://docs.google.com/spreadsheets/d/1TWYoCaPVPllyoZyjOhnPeojfzgTbppMDhpK_r87-duM/edit
- Art Movements: https://artsandculture.google.com/category/art-movement?hl=en-GB
- Artists: https://artsandculture.google.com/category/artist?hl=en-GB
