<template>
    <div class="game-container">
        <table v-show="!isPuzzleSolved">
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
        <table v-show="isPuzzleSolved">
            <tr>
                <td><span>{{ puzzle[0][0] }}</span></td>
                <td><span>{{ puzzle[0][1] }}</span></td>
                <td><span>{{ puzzle[0][2] }}</span></td>
                <td><span>{{ puzzle[0][3] }}</span></td>
                <td><span>{{ puzzle[0][4] }}</span></td>
                <td><span>{{ puzzle[0][5] }}</span></td>
                <td><span>{{ puzzle[0][6] }}</span></td>
                <td><span>{{ puzzle[0][7] }}</span></td>
                <td><span>{{ puzzle[0][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[1][0] }}</span></td>
                <td><span>{{ puzzle[1][1] }}</span></td>
                <td><span>{{ puzzle[1][2] }}</span></td>
                <td><span>{{ puzzle[1][3] }}</span></td>
                <td><span>{{ puzzle[1][4] }}</span></td>
                <td><span>{{ puzzle[1][5] }}</span></td>
                <td><span>{{ puzzle[1][6] }}</span></td>
                <td><span>{{ puzzle[1][7] }}</span></td>
                <td><span>{{ puzzle[1][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[2][0] }}</span></td>
                <td><span>{{ puzzle[2][1] }}</span></td>
                <td><span>{{ puzzle[2][2] }}</span></td>
                <td><span>{{ puzzle[2][3] }}</span></td>
                <td><span>{{ puzzle[2][4] }}</span></td>
                <td><span>{{ puzzle[2][5] }}</span></td>
                <td><span>{{ puzzle[2][6] }}</span></td>
                <td><span>{{ puzzle[2][7] }}</span></td>
                <td><span>{{ puzzle[2][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[3][0] }}</span></td>
                <td><span>{{ puzzle[3][1] }}</span></td>
                <td><span>{{ puzzle[3][2] }}</span></td>
                <td><span>{{ puzzle[3][3] }}</span></td>
                <td><span>{{ puzzle[3][4] }}</span></td>
                <td><span>{{ puzzle[3][5] }}</span></td>
                <td><span>{{ puzzle[3][6] }}</span></td>
                <td><span>{{ puzzle[3][7] }}</span></td>
                <td><span>{{ puzzle[3][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[4][0] }}</span></td>
                <td><span>{{ puzzle[4][1] }}</span></td>
                <td><span>{{ puzzle[4][2] }}</span></td>
                <td><span>{{ puzzle[4][3] }}</span></td>
                <td><span>{{ puzzle[4][4] }}</span></td>
                <td><span>{{ puzzle[4][5] }}</span></td>
                <td><span>{{ puzzle[4][6] }}</span></td>
                <td><span>{{ puzzle[4][7] }}</span></td>
                <td><span>{{ puzzle[4][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[5][0] }}</span></td>
                <td><span>{{ puzzle[5][1] }}</span></td>
                <td><span>{{ puzzle[5][2] }}</span></td>
                <td><span>{{ puzzle[5][3] }}</span></td>
                <td><span>{{ puzzle[5][4] }}</span></td>
                <td><span>{{ puzzle[5][5] }}</span></td>
                <td><span>{{ puzzle[5][6] }}</span></td>
                <td><span>{{ puzzle[5][7] }}</span></td>
                <td><span>{{ puzzle[5][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[6][0] }}</span></td>
                <td><span>{{ puzzle[6][1] }}</span></td>
                <td><span>{{ puzzle[6][2] }}</span></td>
                <td><span>{{ puzzle[6][3] }}</span></td>
                <td><span>{{ puzzle[6][4] }}</span></td>
                <td><span>{{ puzzle[6][5] }}</span></td>
                <td><span>{{ puzzle[6][6] }}</span></td>
                <td><span>{{ puzzle[6][7] }}</span></td>
                <td><span>{{ puzzle[6][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[7][0] }}</span></td>
                <td><span>{{ puzzle[7][1] }}</span></td>
                <td><span>{{ puzzle[7][2] }}</span></td>
                <td><span>{{ puzzle[7][3] }}</span></td>
                <td><span>{{ puzzle[7][4] }}</span></td>
                <td><span>{{ puzzle[7][5] }}</span></td>
                <td><span>{{ puzzle[7][6] }}</span></td>
                <td><span>{{ puzzle[7][7] }}</span></td>
                <td><span>{{ puzzle[7][8] }}</span></td>
            </tr>
            <tr>
                <td><span>{{ puzzle[8][0] }}</span></td>
                <td><span>{{ puzzle[8][1] }}</span></td>
                <td><span>{{ puzzle[8][2] }}</span></td>
                <td><span>{{ puzzle[8][3] }}</span></td>
                <td><span>{{ puzzle[8][4] }}</span></td>
                <td><span>{{ puzzle[8][5] }}</span></td>
                <td><span>{{ puzzle[8][6] }}</span></td>
                <td><span>{{ puzzle[8][7] }}</span></td>
                <td><span>{{ puzzle[8][8] }}</span></td>
            </tr>
        </table>
        <button v-show="!isPuzzleSolved && isPuzzleValid" @click="validatePuzzle()">Solve</button>
        <button v-show="!isPuzzleSolved && isPuzzleValid" @click="addExample()">Try example</button>
        <button v-show="isPuzzleSolved || !isPuzzleValid" @click="clearPuzzle()">Try again</button>
        <p v-show="!isPuzzleValid">Fill some known numbers of sudoku. Valid numbers are 1-9</p>
        <p v-show="isPuzzleValid && !noSolution">Solves a <a href="https://en.wikipedia.org/wiki/Sudoku"
                target="_blank">Sudoku</a> by the
            provided "clues"</p>
        <p v-show="noSolution">This sudoku has not solution</p>
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
            isPuzzleValid: true,
            isPuzzleSolved: false,
            noSolution: false
        };
    },
    methods: {
        validatePuzzle: function () {
            outer_loop:
            for (let i = 0; i < this.puzzle.length; i++) {
                for (let j = 0; j < this.puzzle[i].length; j++) {
                    if (![null, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9].includes(Number(this.puzzle[i][j]))) {
                        this.isPuzzleValid = false;
                        break outer_loop;
                    } else {
                        this.isPuzzleValid = true;
                    }
                }
            }
            if (this.isPuzzleValid) {
                this.preparePuzzle();
                this.returnSolved();
            }
        },
        clearPuzzle: function () {
            this.puzzle = [
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null],
                [null, null, null, null, null, null, null, null, null]
            ];
            this.isPuzzleSolved = false;
            this.isPuzzleValid = true;
            this.noSolution = false;
        },
        returnSolved: function () {
            if (this.solvePuzzle()) {
                this.isPuzzleSolved = true;
            } else {
                this.puzzle = [
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null],
                    [null, null, null, null, null, null, null, null, null]
                ];
                this.isPuzzleSolved = true;
                this.noSolution = true;
            }
        },
        addExample: function () {
            this.puzzle = [[null, null, "3", null, null, "1", null, null, null], ["7", null, null, "8", null, null, "5", "2", null], ["8", null, "4", null, null, null, "6", null, "3"], [null, null, "7", "3", "2", null, null, null, null], ["5", null, null, null, null, null, null, null, "2"], [null, null, null, null, "1", "7", "4", "3", null], [null, "6", "5", null, null, "4", null, null, null], [null, "2", "9", "1", "8", "5", "3", null, "7"], [null, "7", "8", "6", "3", null, "9", "5", "4"]]
        },
        preparePuzzle: function () {
            for (let i = 0; i < this.puzzle.length; i++) {
                for (let j = 0; j < this.puzzle[i].length; j++) {
                    this.puzzle[i][j] = Number(this.puzzle[i][j])
                }
            }
        },
        isNumberValid: function (puzzle, row, col, val) {
            for (let i = 0; i < 9; i++) {
                if (puzzle[row][i] === val) {
                    return false;
                }
            }
            for (let i = 0; i < 9; i++) {
                if (puzzle[i][col] === val) {
                    return false;
                }
            }
            let squareRow = Math.floor(row / 3) * 3;
            let squareCol = Math.floor(col / 3) * 3;
            for (let i = 0; i < 3; i++) {
                for (let j = 0; j < 3; j++) {
                    if (puzzle[squareRow + i][squareCol + j] === val)
                        return false;
                }
            }
            return true;
        },
        findEmptyCell: function (puzzle) {
            for (let row = 0; row < 9; row++) {
                for (let col = 0; col < 9; col++) {
                    if (puzzle[row][col] === 0 || puzzle[row][col] === null) {
                        return [row, col]
                    }
                }
            }
        },
        solvePuzzle: function () {
            let empty = this.findEmptyCell(this.puzzle);
            if (empty) {
                let [row, col] = empty;
                for (let num = 1; num <= 9; num++) {
                    if (this.isNumberValid(this.puzzle, row, col, num)) {
                        this.puzzle[row][col] = num;
                        let result = this.solvePuzzle(this.puzzle);
                        if (result) {
                            return result;
                        } else {
                            this.puzzle[row][col] = 0;
                        }
                    }
                }
                return;
            }
            return this.puzzle;
        }
    }
};
</script>
  
<style scoped>
.game-container {
    position: relative;
    background-color: var(--main-bg-color);
    width: 600px;
    height: 500px;
    margin: 0px;
    padding: 0px;
    text-align: center;
}

p {
    padding: 10px;
    color: var(--dark-font-color);
    border: 2px solid var(--second-main-color);
    text-align: center;
    margin: 10px;
}

table {
    margin: 10px auto;
    border-collapse: collapse;
}

td {
    padding: 5px;
    width: 30px;
    height: 30px;
    text-align: center;
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
    background-color: transparent;
    text-align: center;
    outline: none;
    width: 15px;
}

span {
    padding: 5px;
}

button {
    margin-left: 10px;
    border: none;
    background-color: var(--light-font-color);
    color: var(--dark-font-color);
    padding: 10px;
    border-radius: 20px;
    cursor: pointer;
    letter-spacing: 2px;
    text-align: center;
    display: inline-block;
}

button:hover {
    color: var(--light-font-color);
    background-color: var(--dark-font-color);
}

@media (max-width: 845px) {
    .game-container {
        width: 350px;
        margin: auto;
        height: 550px;
        padding: 5px;
        margin-bottom: 10px;
    }
}
</style>
