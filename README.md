# n8nWorkFlow
My First n8n workflow using AI agent, Telegram

// ✅ Process all Airtable records into a clean JSON array
const cleanedData = $input.all().map(item => {
  const record = item.json;

  return {
    id: record.ID,
    cost: parseFloat(record.Cost),
    category: record.Category,
    name: record.Name,
    brand: record.Brand,
    retail_price: parseFloat(record.Retail_Price),
    profit_margin: parseFloat(record.Retail_Price) - parseFloat(record.Cost),
    department: record.Department,
    sku: record.SKU,
    distribution_center_id: record.distribution_center_ID
  };
});

// ✅ Return a single item with the array inside `records`
return [
  {
    json: {
      records: cleanedData
    }
  }
];


## Airtable is used to store records##
# Link to Airtable https://airtable.com/appDnektMpa8kh9d2/tblRK1n56wqrHelkl/viw9Wc3IPPk1TEa5W?blocks=hide  ##
