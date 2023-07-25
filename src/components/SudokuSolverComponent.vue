<template>
    <div class="game-container">
        <table>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
                <td></td>
            </tr>
            <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </table>
    <p>Solves a <a href="https://en.wikipedia.org/wiki/Sudoku">Sudoku</a> by the provided "clues".</p>
</div></template>
  
<script>
export default {
    name: "Sudoku",
    data: function () {
        return {

        };
    },
    methods: {}
};
</script>
  
<style scoped>.game-container {
    position: relative;
    background-color: var(--main-bg-color);
    width: 600px;
    height: 500px;
}

p {
    padding: 10px;
    color: var(--dark-font-color);
    border: 2px solid var(--second-main-color);
    text-align: center;
    margin: 15px;
}

table {
    margin: 15px auto;
    border-collapse: collapse;
}

td {
    padding: 10px;
    width: 20px;
    height: 20px;
    border-left: 2px solid var(--header-bg-color);
    border-right: 2px solid var(--header-bg-color);
    border-bottom: 2px solid var(--header-bg-color);
}

td:first-child {
    border-left: 2px solid var(--dark-font-color);
}

td:nth-child(3n) {
    border-right: 2px solid var(--dark-font-color);
}

tr:first-child {
    border-top: 2px solid var(--dark-font-color);
}

tr:nth-child(3n) td {
    border-bottom: 2px solid var(--dark-font-color);
}</style>
  