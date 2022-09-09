# Grapevine UI

A semanticly strict, high-level UI component library.  
Powered by [_hyperscript](https://hyperscript.org/).

<br/>

---
## Install

<br/>

---

## Components

Components are defined with the `id` attribute.

<details><summary>Component List</summary><br/>

* [navbar](#navbar)

</details>

<br/>

### Sub-components

Sub-components are defined with the `class` attribute.

<br/>

---

## Navbar
##### Component

1. Must be defined on a `header` element.
2. May contain the following sub-components.
    - hamburger
    - title

#### example

    <header id="navbar">
        
    </header>

<br/>

### Hamburger
##### Sub-component

1. Must be the child of a navbar component.
2. Must be defined on a `button` element.
3. Must conatin 3 span elements.
4. Toggles an offcanvas component.

#### example

    <header id="navbar">
        <button
            class="hamburger"
            _="on click
                toggle .open on me
                then toggle .open on #offcanvas
            end"
        >
            <span></span><span></span><span></span>
        </button>
    </header>

<br/>

### Title
##### Sub-component

1. Must be the child of a navbar component.
2. Must be defined on an `span` element.

#### example

    <header id="navbar">
        <span class="title">Grapevine UI</span>
    </header>

<br/>

---

## Offcanvas
##### Component

1. Must be defined on a `nav` element.
2. Id attribute must end with 'offcanvas'.
2. May contain the following sub-components.
    - nav-elements

#### example

    <nav id="offcanvas">

    </nav>

<br/>

### Nav-elements
##### Sub-component

1. Must be the child of an offcanvas component.
2. Must be defined on a `menu` element.
3. May contain the following sub-components.
    - dropdown
    - dropdown-elements

#### example

    <nav id="offcanvas">
        <menu class="nav-elements">
            <li><a href="#">Page One</a></li>
            <li><a href="#">Page Two</a></li>
            <li><a href="#">Page Three</a></li>
        </menu>
    </nav>

#### Dropdown & Dropdown-elements
##### sub-component

1. Must be the child of a nav-elements sub-component.
2. Dropdown must be defined on a `button` element.
3. Dropdown-elements must be defined on a `menu` element and placed after a dropdown sub-component.
4.  Toggles a dropdown-elements sub-component

#### example

    <nav id="offcanvas">
        <menu class="nav-elements">
            <li><a href="#">Page One</a></li>
            <li>
                <a href="#">Page Two</a>
                <button
                    class="dropdown"
                    _="on click
                        toggle .open on me
                        then toggle .open on the next .dropdown-elements
                    end"></button>
            </li>
            <menu class="dropdown-elements">
                <li><a href="#">Page One</a></li>
                <li><a href="#">Page Two</a></li>
                <li><a href="#">Page Three</a></li>
            </menu>
            <li><a href="#">Page Three</a></li>
            <li>
                <a href="#">Page Four</a>
                <button
                    class="dropdown"
                    _="on click
                        toggle .open on me
                        then toggle .open on the next .dropdown-elements
                    end"></button>
            </li>
            <menu class="dropdown-elements">
                <li><a href="#">Page One</a></li>
                <li><a href="#">Page Two</a></li>
                <li><a href="#">Page Three</a></li>
            </menu>
        </menu>
    </nav>




