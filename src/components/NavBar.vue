<template>
  <nav>
    <details>
        <summary class="menu-icon-btn">
            <svg class="menu-icon" xmlns="http://www.w3.org/2000/svg" height="48" width="48">
                <path d="M6 36v-3h36v3Zm0-10.5v-3h36v3ZM6 15v-3h36v3Z"/>
            </svg>
            <svg class="close-icon" xmlns="http://www.w3.org/2000/svg" height="48" width="48">
                <path d="m12.45 37.65-2.1-2.1L21.9 24 10.35 12.45l2.1-2.1L24 21.9l11.55-11.55 2.1 2.1L26.1 24l11.55 11.55-2.1 2.1L24 26.1Z"/>
            </svg>
        </summary>
        <div class="menu-items">
            <ul>
                <li><a href="/#home">Home</a></li>
                <li><a href="/#calculator">Calculator</a></li>
                <li><a href="/#faq">FAQ</a></li>
                <li><a href="/#inspqoutes">Inspirational Qoutes</a></li>
            </ul>
        </div>
    </details>
  </nav>
</template>

<script>
export default {

}
</script>

<style>

details {
    user-select: none;
    position: relative;
}

.close-icon {
    display: none;
}

summary:hover {
    cursor: pointer;
}

svg {
    fill: var(--dark-color);
}

.menu-items {
    position: absolute;
    right: 5px;
    background-color: var(--text-background);
    min-width: 13rem;
    transition-duration: 2s;
}

ul {
    list-style: none;
    padding: 1rem;
}

a {
    color: var(--dark-color);
    text-decoration: none;
    font-size: larger;
}

a:visited {
    color: var(--dark-color);
}

li:not(:last-child) { 
   margin-bottom: 3rem;  
}

li {
    margin-bottom: .5rem;
}

li:hover {
    cursor: pointer;

}

details[open] .close-icon {
    display: unset;
}

details[open] .menu-icon {
    display: none;
}

.menu-icon-btn::marker {
    display: none;
    content: '';
}

</style>