<template>
    <footer class="footer">
        <div class="foot-flexbox">
            <ul class="foot-nav">
                <li ><a href="#">Home</a></li>
                <li class="nav-pipe"></li>
                <li><a href="#">Portfolio</a></li>
            </ul>
            <div class="foot-copy">
                <p>Copyright © 2018 Told Design</p>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer',
}
</script>

<style lang="scss" scoped>

.footer {
    background-color: #323437;
    padding: 30px;
}

.foot-flexbox {
    display: flex;
    flex-direction: column;
    width: 1000px;
    max-width: 100%;
    margin: 0 auto;

    @media screen and (min-width: 768px) {
        flex-direction: row;
        justify-content: space-between;
    }
}

ul.foot-nav {
    list-style-type: none;
    margin: 0 0 75px 0;
    padding: 0;

    @media screen and (min-width: 768px) {
        margin: 0;
    }

    li {
        @media screen and (min-width: 768px) {
            display: inline;
            padding: 0 25px;

            &.nav-pipe {
                padding: 0 2px 0 0;
                background-color: #50ada2;
            }
        }
    }
}

.foot-nav li a, .foot-copy p {
    color: #FCFAF9;
    text-decoration: none;
}

</style>
