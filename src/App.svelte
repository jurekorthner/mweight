<script>
    let height = 0;
    let activityLevel = 0;
    let bodycount = 0;
    let candycrushLvl = 0;

    let weight = 0;

    function calculate() {
        if (activityLevel == 0) {
            return;
        }
        if (height <= 0) {
            return;
        }
        if (bodycount <= 0) {
            return;
        }
        if (candycrushLvl <= 0) {
            return;
        }
        if (activityLevel === "Only sitting around and eating chips") {
            activityLevel = 3;
        }
        if (activityLevel === "Getting up and walking to the fridge") {
            activityLevel = 2;
        }
        if (activityLevel === "Getting actively fucked") {
            activityLevel = 1;
        }
        console.log(activityLevel);
        let candycrushLvl2 = Math.max(candycrushLvl + 500, 2000);
        weight = height * bodycount * activityLevel * candycrushLvl2 * 5000;
        weight += Math.floor(Math.random() * weight * 0.2) - weight * 0.1;

        let element = document.getElementById("result");
        element.style.display = "flex";
        element.scrollIntoView({ behavior: "smooth" });
    }
</script>

<div id="input" class="main">
    <div id="row">
        <h1 class="heading">Calculate the weight of your mom</h1>

        <div id="inputContainer">
            <label class="input-label" for="iHeight">Height in cm</label>
            <input type="number" class="input-field" bind:value={height} />

            <label class="input-label" for="iActValue">Activity Level</label>
            <select class="input-field" bind:value={activityLevel}>
                <option selected="selected" name="0"
                    >Only sitting around and eating chips</option
                >
                <option selected="selected" name="1"
                    >Getting up and walking to the fridge</option
                >
                <option selected="selected" name="2"
                    >Getting actively fucked</option
                >
            </select>

            <label type="number" class="input-label" for="iBodyCount"
                >Bodycount</label
            >
            <input class="input-field" bind:value={bodycount} />

            <label type="number" class="input-label" for="iCandycrushLvl"
                >Candycrush Level</label
            >
            <input class="input-field" bind:value={candycrushLvl} />

            <br />
            <button type="submit" id="submitBtn" on:click={calculate}
                >Calculate</button
            >
        </div>
    </div>
</div>
<div id="result" class="main">
    <div id="row">
        <h1>Holy shit your mom is a motherfucking CHONKER!</h1>

        <div id="resultsContainer">
            <h1 class="resultH">{weight} kg</h1>

            <h1>= {Math.floor(weight / 40000)} Trucks!</h1>
            <h1>= {Math.floor(weight / 200000)} Houses!</h1>
            <h1>= {Math.floor(weight / 370000000)} Empire State Buildings!</h1>
            <h1>
                = {Math.floor(weight / 6000000000)} times the Cheops-Pyramid!
            </h1>
        </div>
    </div>
</div>
<style>
    .input-field {
        font-size: 1.5rem;
        border-radius: 0.7rem;
        padding: 0.5rem;
        text-align: center;
        margin-bottom: 1.5rem;
        width: 50%;        
    }

    .input-label {
        font-size: 1.4rem;
        margin-bottom: 0.3rem;
    }

    .resultH {
        font-size: 5rem;
    }

    .main {
        flex-direction: column;
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .heading {
        font-size: 3rem;
        margin-bottom: 3rem;
    }

    .cc {
        transform: translateY(-3rem);
        margin-left: 0.7rem;
    }

    #row {
        width: auto;
    }

    #inputContainer {
        text-align: center;
    }

    #resultsContainer {
        text-align: center;
    }

    #result {
        display: none;
    }

    #submitBtn {        
        font-size: 1.3rem;
        background-color: #eee;
        outline: #444;
        outline-style: solid;
        outline-width: 1px;
        margin-top: 0.5rem;
        border-radius: 1.2rem;
        padding: 0.7rem;
    }

    #submitBtn:hover {        
        cursor: pointer;
    }

    label {
        font-weight: bold;
    }
</style>
