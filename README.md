<?php

function calculateBill($units)
{
    $bill = 0;

    if ($units <= 100) {
        $bill = $units * 1.50;
    } 
    elseif ($units <= 200) {
        $bill = (100 * 1.50) + (($units - 100) * 2.50);
    } 
    elseif ($units <= 500) {
        $bill = (100 * 1.50) + (100 * 2.50) + (($units - 200) * 4.00);
    } 
    else {
        $bill = (100 * 1.50) + (100 * 2.50) + (300 * 4.00) + (($units - 500) * 6.00);
    }

    return $bill;
}

$units = 350;
$totalBill = calculateBill($units);

echo "Units Consumed: " . $units . "<br>";
echo "Total Electricity Bill: ₹" . $totalBill;

?>
Units Consumed: 350
Total Electricity Bill: ₹900
