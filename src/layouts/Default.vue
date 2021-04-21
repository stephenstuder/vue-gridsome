<template>
    <body class="layout dark oled">
        <header>
            <strong>
                <g-link to="/">{{ $static.metadata.siteName }}</g-link>
            </strong>
            <nav>
                <g-link to="/">Home</g-link>
                <g-link to="/about/">About</g-link>
            </nav>
        </header>
        <slot />
    </body>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>
