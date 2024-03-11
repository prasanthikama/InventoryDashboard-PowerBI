# InventoryDashboard-PowerBI
 The goal of this project is to increase sales by analyzing inventory data.
InventoryDashboard-PowerBI
The goal of this project is to increase sales by analyzing inventory data.

Stock Optimization: Ensure that popular products are well-stocked to meet customer demand. Prevent stockouts and backorders that can result in lost sales opportunities.

Demand Forecasting: Use historical inventory data to forecast future demand. Anticipate trends and adjust stock levels accordingly, minimizing excess inventory or stockouts.

Promotion and Marketing Strategy: Identify slow-moving items and develop targeted promotions to boost sales. Tailor marketing strategies based on inventory insights to maximize the impact of promotions.

Supplier Management: Evaluate supplier performance using inventory data. Ensure timely and reliable product deliveries to maintain consistent stock levels.

Avg. Days pre order = AVERAGE('Inventory Stock Control'[Days Per Reorder])

Decommissioned Products = CALCULATE(DISTINCTCOUNT('Inventory Stock Control'[Item Name]),'Inventory Stock Control'[Item Discontinued?]="Yes")

Expected Costs for Upcoming Re-stocking Requirements = CALCULATE ( [Total Costs Of Re-Order Products], FILTER ( 'Inventory Stock Control', 'Inventory Stock Control'[Stock Quantity] <= 'Inventory Stock Control'[Reorder Level] * 1.8 ) )

How Old is Inventory = DATEDIFF(MAX('Inventory Stock Control'[Date Of Last Order]),TODAY(),DAY) Inv. Purchased Last 30 Days = CALCULATE ( [Total Quantity Sold], DATESBETWEEN ( 'Dates'[Date], LASTDATE ( 'Sales Data'[OrderDate] ) - 30, LASTDATE ( 'Sales Data'[OrderDate] ) ) )

Inv. Restocking Costs = CALCULATE ( [Total Costs Of Re-Order Products], FILTER ( 'Inventory Stock Control', 'Inventory Stock Control'[Stock Quantity] < 'Inventory Stock Control'[Reorder Level]

))

Inventory Value = SUM('Inventory Stock Control'[Total Value])

Re-Order Products = CALCULATE ( DISTINCTCOUNT ( 'Inventory Stock Control'[Item Name] ), FILTER ( 'Inventory Stock Control', 'Inventory Stock Control'[Stock Quantity] <= 'Inventory Stock Control'[Reorder Level] ) )

Stock Quantity Status = IF ( [Total Stock Inventory], IF ( [Total Stock Inventory] <= MAX ( 'Inventory Stock Control'[Reorder Level] ), "Needs Reodering", IF ( [Total Stock Inventory] <= MAX ( 'Inventory Stock Control'[Reorder Level] ) * 1.8, "Low Stock", "Safety Stock Level" ) ), BLANK ()

Total Costs Of Re-Order Products = SUMX('Inventory Stock Control', 'Inventory Stock Control'[Cost Per Item] * 'Inventory Stock Control'[Item Reorder Quantity]) )

Total Customers = DISTINCTCOUNT('Customers'[CustomerName])

About
The goal of this project is to increase sales by analyzing inventory data.

Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Releases
No releases published
Create a new release
Packages
No packages published
Publish your first package
Footer
© 2
