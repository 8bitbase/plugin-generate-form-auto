# plugin-generate-form-auto
JS plugin for form component: input list item, button add item row. <br />
<br />
Author: github.com/lechidung<br />
<br />
## 1. Install plugin

```
# NEEDED CSS BOOTSTRAP 3
# NEEDED JS
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.0/jquery.min.js"></script>
<script src="js/plugin-generate-form-automation.js"></script>
```

## 2. Use plugin express
### 1. Template
```
<script id="template_award" type="text">
    <div class="form-group">
        <div class="col-sm-2">
            <label class="control-label lcd-current-row">Award</label>
        </div>
        <div class="col-sm-5">
            <input class="form-control" name="award[]quantity[]" type="number" maxlength="11" min="1" max="99999999999" value="" />
        </div>
        <div class="col-sm-1">
            <label class="control-label"> unit </label>
        </div>
    </div>
</script>
```
### 2. Default value
```
var defaultAward = [{"quantity":3},{"quantity":5},{"quantity":10}];
```
### 3. Config plugin
```
<script type="text/javascript">
    // Template
    var templateAward = $("#template_award").html();
    // Value
    var defaultAward = [{"quantity":3},{"quantity":5},{"quantity":10}];
    // Config to load plugin
    $("#award-list-2").makeInputForm({
        "button_add": {
            "active": true,
            "lable": "+ Add award (max 10 row)"
        },
        "container_id": "list-item-2", // distinct container
        "minRow": "1",
        "maxRow": "10",
        "data": defaultAward,
        "mapData": {'quantity': 'award[]quantity[]'},
        "template": "award",
        "elements": templateAward
    });
</script>
```
## 3. Other parameters

if label add class "lcd-current-row", when render form system auto add index current row before value in label.