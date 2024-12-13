# Coding Standards

This document outlines the coding standards and best practices to be followed for the application.

## PHP Standards

### General
- Follow the [PSR-12](https://www.php-fig.org/psr/psr-12/) coding standard.
- Use meaningful and descriptive variable, function, and class names.
- Avoid using magic numbers; define constants instead.

### Formatting
- Indent code using 4 spaces.
- Use single quotes for strings unless the string contains variables that need to be parsed.
- Place opening braces on the same line as the declaration.

```php
// Correct
if ($condition) {
    // code
}

// Incorrect
if ($condition)
{
    // code
}
```

### Classes and Methods

- Use CamelCase for class names and camelCase for method names.
- Each class should be in its own file. 
- Follow the Single Responsibility Principle (SRP); a class should have only one responsibility.
    
```php
class UserController extends Controller {
    public function index() {
    // method code
    }
}
```

### Naming Conventions

- Classes and interfaces: `PascalCase`
- Methods and variables: `camelCase`
- Constants: `UPPER_CASE_WITH_UNDERSCORES`

### Comments and Documentation

- Use PHPDoc for class, method, and function documentation. 
- Write meaningful comments explaining complex logic or decisions.

``` javascript
/**
* Calculate the area of a circle.
*
* @param float $radius
* @return float
*/
    function calculateCircleArea(float $radius): float {
        return pi() * $radius * $radius;
    }
```

## JavaScript Standards

### General

- Follow the Airbnb JavaScript Style Guide.
- Use `const` and `let` instead of `var` for variable declarations.
- Use arrow functions where appropriate.

``` javascript
    // Correct
    const multiply = (a, b) => a * b;
    
    // Incorrect
    var multiply = function(a, b) {
        return a * b;
    };
```

### Formatting

- Indent code using 2 spaces.
- Use single quotes for strings.
- Place opening braces on the same line as the declaration.

``` javascript
// Correct
if (condition) {
    // code
}

// Incorrect
if (condition)
{
    // code
}
```

### Naming Conventions

- Variables and functions: `camelCase`
- Constants: `UPPER_CASE_WITH_UNDERSCORES` 
- Classes: `PascalCase`
    

### Comments and Documentation

- Use JSDoc for function and method documentation.
- Write meaningful comments explaining complex logic or decisions.

```javascrip
/**
* Calculate the area of a circle.
*
* @param {number} radius
* @return {number}
*/
function calculateCircleArea(radius) {
    return Math.PI * radius * radius;
}
```

## HTML/CSS Standards

### General

- Follow the W3C HTML and CSS standards.    
- Use semantic HTML tags (e.g., `<header>`, `<footer>`, `<article>`).
    
### Formatting

- Indent code using 2 spaces.    
- Use lowercase for element names, attributes, and values (except for boolean attributes).

```html
<!-- Correct -->
<input type="text" disabled>

<!-- Incorrect -->
<Input Type="Text" Disabled>
```

### CSS/SCSS

- Use a modular approach (e.g., BEM methodology) for naming classes.
- Avoid inline styles; use classes instead.
- Use variables for colors, fonts, and other reusable values.

```
// Correct
$primary-color: #3498db;

.button {
    background-color: $primary-color;
}

// Incorrect
<button style="background-color: #3498db;">Click me</button>
```

## Version Control

### Git

- Use meaningful commit messages.
- Commit small, atomic changes frequently.
- Follow the Git branching model.

```
# Correct
git commit -m "Add user authentication"

# Incorrect
git commit -m "Fixed stuff"
```

## Testing

### PHP

- Write unit tests for all functions and methods using PHPUnit.
- Use Mockery for mocking dependencies in tests.

### JavaScript

- Write unit tests for all functions and methods using a testing framework like Jest.
- Ensure comprehensive test coverage for all critical code paths.
