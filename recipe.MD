# Recipe

- Create an object to hold information on your favourite recipes. It should have properties for:
    - title (a string)
    - servings (a number)
    - ingredients (an array of strings)
    - directions (a string)
- List all recipes
- Create a loop to list all of the ingredients.

```
FUNCTION list_recipes(recipe_array)
    FOR EACH recipe in recipe_array
        PRINT(recipe.Title)
        PRINT(' (serves ')
        PRINT(reciple.servings)
        PRINT(')')
        PRINT(newline)

        PRINT('Ingredients', newline)
        FOR EACH ingredient in recipe.ingredients
            PRINT('- ', ingredient, newline)
        
        PRINT('Directions', newline)
        FOR EACH direction in recipe.directions
            PRINT('- ', direction, newline)

        PRINT(newline)
```

```
FUNCTION list_all_ingredients(recipe_array)
    distinct_ingredients = []
    FOR EACH recipe in recipe_array
        FOR EACH ingredient in recipe.ingredients
            IF ingredient NOT IN distinct_ingredients
                APPEND ingredient to distinct_ingredients
            
    SORT distinct_ingredients
    PRINT('Ingredients for all recipes')
    FOR EACH ingredient in distinct_ingredients
        PRINT('- ', ingredient, newline)
```

**Tested Solution in Python**

```
from collections import namedtuple

recipe = namedtuple('recipe', 'title servings ingredients directions')

recipe1 = recipe('Cheese on toast', 1, 'bread butter cheese marmite'.split(),
                  ('toast the bread',
                   'spread butter on the toast',
                   'spread marmite on the toast',
                   'grate some cheese on the toast',
                   'sprinkle grated cheese on the toast',
                   'place under the grill until cheese is melted')
                )

recipe2 = recipe('Jam Sandwich', 1, 'bread butter jam'.split(),
                  ('spread butter on the bread',
                   'spread jam on the bread',
                   'eat the bread')
                )

recipes= [recipe1, recipe2]

def list_recipes(recipes):
    for recipe in recipes:
        print(f"=== {recipe.title} (serves {recipe.servings}) ===")
        print('INGREDIENTS')
        for ingredient in recipe.ingredients:
            print('-', ingredient)
        print('DIRECTIONS')
        for direction in recipe.directions:
            print('-', direction)
        print()

def list_all_ingredients(recipes):
    all_ingredients = []
    for recipe in recipes:
        for ingredient in recipe.ingredients:
            if ingredient not in all_ingredients:
                all_ingredients.append(ingredient)
    print('=== Ingredients for all recipes ===')
    for ingredient in sorted(all_ingredients):
        print(f"- {ingredient}")

list_recipes(recipes)
list_all_ingredients(recipes)

>>> === Cheese on toast (serves 1) ===
>>> INGREDIENTS
>>> - bread
>>> - butter
>>> - cheese
>>> - marmite
>>> DIRECTIONS
>>> - toast the bread
>>> - spread butter on the toast
>>> - spread marmite on the toast
>>> - grate some cheese on the toast
>>> - sprinkle grated cheese on the toast
>>> - place under the grill until cheese is melted
>>> 
>>> === Jam Sandwich (serves 1) ===
>>> INGREDIENTS
>>> - bread
>>> - butter
>>> - jam
>>> DIRECTIONS
>>> - spread butter on the bread
>>> - spread jam on the bread
>>> - eat the bread
>>> 
>>> === Ingredients for all recipes ===
>>> - bread
>>> - butter
>>> - cheese
>>> - jam
>>> - marmite
```