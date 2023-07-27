<template>
    <div class="game-container">
        <table>
            <tr>
                <td><input v-model="puzzle[0][0]"></td>
                <td><input v-model="puzzle[0][1]"></td>
                <td><input v-model="puzzle[0][2]"></td>
                <td><input v-model="puzzle[0][3]"></td>
                <td><input v-model="puzzle[0][4]"></td>
                <td><input v-model="puzzle[0][5]"></td>
                <td><input v-model="puzzle[0][6]"></td>
                <td><input v-model="puzzle[0][7]"></td>
                <td><input v-model="puzzle[0][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[1][0]"></td>
                <td><input v-model="puzzle[1][1]"></td>
                <td><input v-model="puzzle[1][2]"></td>
                <td><input v-model="puzzle[1][3]"></td>
                <td><input v-model="puzzle[1][4]"></td>
                <td><input v-model="puzzle[1][5]"></td>
                <td><input v-model="puzzle[1][6]"></td>
                <td><input v-model="puzzle[1][7]"></td>
                <td><input v-model="puzzle[1][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[2][0]"></td>
                <td><input v-model="puzzle[2][1]"></td>
                <td><input v-model="puzzle[2][2]"></td>
                <td><input v-model="puzzle[2][3]"></td>
                <td><input v-model="puzzle[2][4]"></td>
                <td><input v-model="puzzle[2][5]"></td>
                <td><input v-model="puzzle[2][6]"></td>
                <td><input v-model="puzzle[2][7]"></td>
                <td><input v-model="puzzle[2][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[3][0]"></td>
                <td><input v-model="puzzle[3][1]"></td>
                <td><input v-model="puzzle[3][2]"></td>
                <td><input v-model="puzzle[3][3]"></td>
                <td><input v-model="puzzle[3][4]"></td>
                <td><input v-model="puzzle[3][5]"></td>
                <td><input v-model="puzzle[3][6]"></td>
                <td><input v-model="puzzle[3][7]"></td>
                <td><input v-model="puzzle[3][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[4][0]"></td>
                <td><input v-model="puzzle[4][1]"></td>
                <td><input v-model="puzzle[4][2]"></td>
                <td><input v-model="puzzle[4][3]"></td>
                <td><input v-model="puzzle[4][4]"></td>
                <td><input v-model="puzzle[4][5]"></td>
                <td><input v-model="puzzle[4][6]"></td>
                <td><input v-model="puzzle[4][7]"></td>
                <td><input v-model="puzzle[4][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[5][0]"></td>
                <td><input v-model="puzzle[5][1]"></td>
                <td><input v-model="puzzle[5][2]"></td>
                <td><input v-model="puzzle[5][3]"></td>
                <td><input v-model="puzzle[5][4]"></td>
                <td><input v-model="puzzle[5][5]"></td>
                <td><input v-model="puzzle[5][6]"></td>
                <td><input v-model="puzzle[5][7]"></td>
                <td><input v-model="puzzle[5][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[6][0]"></td>
                <td><input v-model="puzzle[6][1]"></td>
                <td><input v-model="puzzle[6][2]"></td>
                <td><input v-model="puzzle[6][3]"></td>
                <td><input v-model="puzzle[6][4]"></td>
                <td><input v-model="puzzle[6][5]"></td>
                <td><input v-model="puzzle[6][6]"></td>
                <td><input v-model="puzzle[6][7]"></td>
                <td><input v-model="puzzle[6][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[7][0]"></td>
                <td><input v-model="puzzle[7][1]"></td>
                <td><input v-model="puzzle[7][2]"></td>
                <td><input v-model="puzzle[7][3]"></td>
                <td><input v-model="puzzle[7][4]"></td>
                <td><input v-model="puzzle[7][5]"></td>
                <td><input v-model="puzzle[7][6]"></td>
                <td><input v-model="puzzle[7][7]"></td>
                <td><input v-model="puzzle[7][8]"></td>
            </tr>
            <tr>
                <td><input v-model="puzzle[8][0]"></td>
                <td><input v-model="puzzle[8][1]"></td>
                <td><input v-model="puzzle[8][2]"></td>
                <td><input v-model="puzzle[8][3]"></td>
                <td><input v-model="puzzle[8][4]"></td>
                <td><input v-model="puzzle[8][5]"></td>
                <td><input v-model="puzzle[8][6]"></td>
                <td><input v-model="puzzle[8][7]"></td>
                <td><input v-model="puzzle[8][8]"></td>
            </tr>
        </table>
        <button @click="validate()">Solve</button>
        <p v-show="!isPuzzleValid">Fill some known numbers of sudoku. Valid numbers are 1-9.</p>
        <p>Solves a <a href="https://en.wikipedia.org/wiki/Sudoku">Sudoku</a> by the provided "clues".</p>
    </div>
</template>
  
<script>
export default {
    name: 'Sudoku',
    data: function () {
        return {
            puzzle: [
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null]
            ],
            isPuzzleValid: true
        };
    },
    methods: {
        validate: function () {
            outer_loop:
            for (let i = 0; i < this.puzzle.length; i++) {
                for (let j = 0; j < this.puzzle[i].length; j++) {
                    if (![0, 1, 2, 3, 4, 5, 6, 7, 8, 9].includes(Number(this.puzzle[i][j]))) {
                        this.isPuzzleValid = false;
                        break outer_loop;
                    } else {
                        this.isPuzzleValid = true;
                    }
                }
            }
            if (this.isPuzzleValid) this.solvePuzzle();
        },
        solvePuzzle: function () {
            console.log('solved')
        }
    }
};
</script>
  
<style scoped>
.game-container {
    position: relative;
    background-color: var(--main-bg-color);
    width: 600px;
    height: 650px;
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
}

input {
    border: none;
    width: 15px;
    background-color: transparent;
    text-align: center;
    outline: none;
    font-size: 18px;
}

button {
    margin: auto;
    border: none;
    background-color: var(--light-font-color);
    color: var(--dark-font-color);
    padding: 15px;
    border-radius: 20px;
    cursor: pointer;
    font-size: 20px;
    letter-spacing: 2px;
    text-align: center;
    display: block;
}

button:hover {
    color: var(--light-font-color);
    background-color: var(--dark-font-color);
}
</style>
  