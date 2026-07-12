![swaying-image (2)](https://github.com/user-attachments/assets/6a7a657a-7432-4959-8cf2-36fc860b1f8b)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>System Analyzer</title>

<style>
body{
    margin:0;
    background:#000;
    color:#00ff66;
    font-family:Consolas, monospace;
    overflow:hidden;
}

.container{
    padding:20px;
}

h1{
    text-align:center;
    text-shadow:0 0 15px #00ff66;
}

.console{
    border:2px solid #00ff66;
    padding:15px;
    height:400px;
    overflow-y:auto;
    background:rgba(0,255,100,0.05);
    box-shadow:0 0 20px #00ff66;
}

.progress{
    margin-top:20px;
    width:100%;
    height:20px;
    border:1px solid #00ff66;
}

.bar{
    width:0%;
    height:100%;
    background:#00ff66;
    transition:width .2s;
}

.cursor{
    display:inline-block;
    width:10px;
    background:#00ff66;
    animation:blink 1s infinite;
}

@keyframes blink{
    50%{
        opacity:0;
    }
}
</style>
</head>
<body>

<div class="container">

<h1>SYSTEM ANALYZER</h1>

<div class="console" id="console"></div>

<div class="progress">
    <div class="bar" id="bar"></div>
</div>

</div>

<script>

const consoleBox = document.getElementById("console");
const bar = document.getElementById("bar");

const logs = [
"Initializing analysis...",
"Loading system modules...",
"Checking CPU...",
"Checking RAM...",
"Scanning directories...",
"Analyzing source files...",
"Parsing HTML...",
"Parsing CSS...",
"Parsing JavaScript...",
"Searching dependencies...",
"Checking Git repository...",
"Running syntax analysis...",
"Inspecting functions...",
"Optimizing assets...",
"Calculating complexity...",
"Building dependency graph...",
"Generating report...",
"No critical issues found.",
"Analysis complete."
];

let i = 0;

function addLine(){

    if(i >= logs.length){
        return;
    }

    const line = document.createElement("div");
    line.innerHTML = "> " + logs[i] + " <span class='cursor'></span>";

    consoleBox.appendChild(line);
    consoleBox.scrollTop = consoleBox.scrollHeight;

    bar.style.width = ((i+1)/logs.length*100)+"%";

    i++;

    setTimeout(addLine,700);

}

addLine();

</script>

</body>
</html>
