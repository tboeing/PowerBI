MaxMin = 
Var SupplyFC = [Supply Forecast Szenario all (pc)]
Var MaxSFCOverall =
MAXX(
    ALLSELECTED('dim Calendar'[YearAsInteger]; 'dim Calendar'[YearQuarter]);
    CALCULATE([Supply Forecast Szenario all (pc)])
)
Var MinSFCOverall =
MINX(
    ALLSELECTED('dim Calendar'[YearAsInteger]; 'dim Calendar'[YearQuarter]);
    Calculate([Supply Forecast Szenario all (pc)])
)
VAR Result =
SWITCH(
    TRUE;
    SupplyFC = MaxSFCOverall; "#22957e";
    SupplyFC = MinSFCOverall; "#ff908c";
    "#7bc8fe"
)
RETURN
Result
