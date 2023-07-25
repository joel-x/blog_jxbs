# Search

## Implementation

Add the following code to your module list in the `config/_default/module.toml` file.

```toml
[[imports]]
path = "github.com/gethugothemes/hugo-modules/search"
```

Add the following code to your `asstes/scss/main.scss` or `asstes/scss/style.scss` file.

```scss
@import 'search';
```

Add the following code to your `head.html` file.

```html
{{ partial "search-index.html" . }}
```

Add the following code to your js plugins list in the `config.toml` file.

```html
[[params.plugins.js]]
link = "js/search.js"
```

Add some following configuration to your `config/_default/config.toml` file.

```toml
############################# Outputs ##############################
[outputs]
home = ["SearchIndex"]

############################ Output Format ###########################
[outputFormats]
[outputFormats.SearchIndex]
mediaType = "application/json"
baseName = "searchindex"
isPlainText = true
notAlternative = true
```

<hr>

## Options

```toml
[search]
enable = true
primary_color = "#ce8460"
include_sections = ["post", "shop"] # if `include_sections` empty, then section's will come from `mainSections`
include_all_sections = false # if `include_all_sections` is true, then comment out the `include_sections`
show_image = true
show_description = true
show_tags = true
show_categories = true
```

## i18n

```yaml
- id: search_input_placeholder
  translation: Search Here

- id: no_results_for
  translation: No results for

- id: empty_search_results_placeholder
  translation: Type something to search..
```

<hr>

## Search Style

There are two search types.
| 1. As a Popup      | 2. Within a Page |
| :-----------: | :-----------: |
| ![image](https://github.com/gethugothemes/hugo-modules/assets/87603786/daf67039-f84c-4799-95b8-4d647e0f535f)| ![image](https://github.com/gethugothemes/hugo-modules/assets/87603786/84ab4cc1-e8fd-460c-95f1-e5432b8b792b) |
| [Live Example](https://demo.gethugothemes.com/bookworm/)| [Live Example](https://demo.gethugothemes.com/logbook/) |

## Use it as a modal

Add this code to where you want to place the search Button or Link

```html
{{ if site.Params.search.enable }}
  <button data-target="search-modal">Search Button</button>
{{ end }}
```

and Add this partial to your `header.html` or inside your base template

```html
{{ partial "search-modal.html" (dict "Context" . "Class" "your-custom-class") }}
```

NOTE : Use `Ctrl + K` or `Command + K` to Search, `ESC` to close, `ArrowUp` and `ArrowDown` key to navigate and `Enter` key to select.

### Use it as a page

Use this as your search input component

```html
{{ if site.Params.search.enable }}
<form action="{{ `search`| relLangURL }}">
  <input name="s" type="search" placeholder="{{ i18n `search_input_placeholder`}}">
  <button type="submit">Search</button>
</form>
{{ end }}
```

and Add this partial inside your search page

```html
{{ partial "search-page.html" (dict "Context" . "Class" "your-custom-class") }}
```

<hr>

or customise the search page

```html
{{ with site.Params.search }}
  {{ if .enable }}
    <script id="search-result-item-template" type="text/x-js-template">
      <div class="search-result-item">
        <div class="search-image">
          #{image}
        </div>
        <div class="search-content-block">
          <a href="#{slug}" class="search-title">#{title}</a>
          <p class="search-description">#{description}</p>
          <p class="search-content">#{content}</p>
          <div class="search-info">
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="currentColor" viewBox="0 0 16 16" style="margin-top:-2px">
                <path d="M11 0H3a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h8a2 2 0 0 0 2-2 2 2 0 0 0 2-2V4a2 2 0 0 0-2-2 2 2 0 0 0-2-2zm2 3a1 1 0 0 1 1 1v8a1 1 0 0 1-1 1V3zM2 2a1 1 0 0 1 1-1h8a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V2z"/>
              </svg>
              #{categories}
            </div>
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="currentColor" viewBox="0 0 16 16">
                <path d="M3 2v4.586l7 7L14.586 9l-7-7H3zM2 2a1 1 0 0 1 1-1h4.586a1 1 0 0 1 .707.293l7 7a1 1 0 0 1 0 1.414l-4.586 4.586a1 1 0 0 1-1.414 0l-7-7A1 1 0 0 1 2 6.586V2z"/>
                <path d="M5.5 5a.5.5 0 1 1 0-1 .5.5 0 0 1 0 1zm0 1a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3zM1 7.086a1 1 0 0 0 .293.707L8.75 15.25l-.043.043a1 1 0 0 1-1.414 0l-7-7A1 1 0 0 1 0 7.586V3a1 1 0 0 1 1-1v5.086z"/>
              </svg>
              #{tags}
            </div>
          </div>
        </div>
      </div>
    </script>
    <div
      class="search-wrapper search-page {{ $class }}"
      data-image="{{ site.Params.search.show_image | default false }}"
      data-description="{{ site.Params.search.show_description | default true }}"
      data-tags="{{ site.Params.search.show_tags | default true }}"
      data-categories="{{ site.Params.search.show_categories | default true }}"
      style="--color-primary: {{ site.Params.search.primary_color | default `#7f0ec6` }}">
      <div class="search-wrapper-content">
        <div class="search-input-body">
          <input
            id="search-input"
            type="text"
            class="!px-4"
            data-search-input
            placeholder="{{ i18n `search_input_placeholder` | default .input_placeholder }}"
            aria-label="Search"
            aria-describedby="Search"
            autocomplete="off"
            autofocus />
        </div>
        <span class="search-result-info"></span>
        <div class="search-wrapper-body">
          <div class="search-result" data-search-result></div>
          <label class="search-result-empty" for="search-input">
            {{ i18n `empty_search_results_placeholder` }}
          </label>
        </div>
      </div>
    </div>
    <script>
      // Remove Search Modal if it is a Search Page
      const removeSearchModal = document.querySelector('.search-modal');
      if (removeSearchModal) {removeSearchModal.remove()}
    </script>
  {{ end }}
{{ end }}
```
