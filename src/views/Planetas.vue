<template>
    <div>
        <div>
            <button @click="option('marte')">Marte</button>
            <button @click="option('plutao')">Plutao</button>
            <button @click="option('venus')">Venus</button>
        </div>
        <div>
            <keep-alive>
                <component :is="component_selected" />
            </keep-alive>
        </div>
    </div>
</template>

<script>
import Marte from '../components/Marte.vue';
import Plutao from '../components/Plutao.vue';
import Venus from '../components/Venus.vue';

export default {
    components: { Marte, Plutao, Venus },
    data() {
        return {
            component_selected: 'Marte',
        };
    },
    methods: {
        option(planet) {
            const options = {
                marte: 'Marte',
                plutao: 'Plutao',
                venus: 'Venus',
            };

            const exists = options.hasOwnProperty(planet);

            if (exists) {
                this.component_selected = options[planet];
            }
        },
    },
};
</script>
