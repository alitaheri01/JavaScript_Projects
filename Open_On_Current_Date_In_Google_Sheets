function SELECT_TODAY_DATE() {
    try {
        var activeSheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
        var lastCell = activeSheet.getRange(activeSheet.getMaxRows(), activeSheet.getMaxColumns());
        var searchRange = activeSheet.getRange("C2:C1000");
        var breakOuterFor = false;
        var today = new Date();
        // var today = new Date(2020, 10, 1);
        today = new Date(today.getFullYear(), today.getMonth(), today.getDate());
        var values = searchRange.getValues();
        var x = 0;
        var y = 0;
        for (x = 0; x < values.length; x++) {
            for (y = 0; y < values[x].length; y++) {
                if (values[x][y]) {
                    var value = new Date(values[x][y]);
                    if (value.getTime() == today.getTime()) {
                        console.log(values[x][y]);
                        // var activeRange = activeSheet.getRange(x + 2, y + 1);
                        // activeSheet.setActiveRange(activeRange);
                        breakOuterFor = true;
                        break;
                    }
                }
            }
            if (breakOuterFor) {
                break;
            }
        }
        
        if (breakOuterFor) {
            activeSheet.setActiveRange(lastCell);
            SpreadsheetApp.flush();
            activeSheet.getRange(x + 2, y + 1).activate();
        }
    } catch (e) {
        alert('SELECT_TODAY_DATE : ' + e);
    }
}
