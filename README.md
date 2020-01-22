# CRUD with JavaScript 

## validations with JS

```
function validation() {
    var desc = document.getElementById("desc").value;
    var amount = document.getElementById("amount").value;
    var value = document.getElementById("value").value;
    var errors = "";
    document.getElementById("errors").style.display = "none";
    if (desc === "") {
        errors += '<p>Fill out description</p>';
    }
    if (amount === "") {
        errors += '<p>Fill out a quantity</p>';
    } else if (amount != parseInt(amount)) {
        errors += '<p>Fill out a valid amount</p>';
    }
    if (value === "") {
        errors += '<p>Fill out a value</p>';
    } else if (value != parseFloat(value)) {
        errors += '<p>Fill out a valid value</p>';
    }

    if (errors != "") {
        document.getElementById("errors").style.display = "block";
        document.getElementById("errors").style.backgroundColor = "rgba(85, 85, 85, 0.3)";
        document.getElementById("errors").style.color = "white";
        document.getElementById("errors").style.padding = "10px";
        document.getElementById("errors").style.margin = "10px";
        document.getElementById("errors").style.borderRadius = "13px";

        document.getElementById("errors").innerHTML = "<h3>Error:</h3>" + errors;
        return 0;
    } else {
        return 1;
    }
}
```

### Save on Storage to Browser

```
function saveListStorage(list) {
    var jsonStr = JSON.stringify(list);
    localStorage.setItem('list', jsonStr);
}

function initListStorage() {
    var testList = localStorage.getItem('list');
    if (testList) {
        list = JSON.parse(testList);
    }

    setList(list);
}


initListStorage();
```