<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bandicoots in Australia</title>
    <!-- Include the Vega-Lite and Vega-Embed libraries -->
    <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
    <script src="https://cdn.jsdelivr.net/npm/vega-lite@4"></script>
    
   
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

</
</head>
<body>
    <!-- Container for the Vega-Lite visualization -->
    
   
<div id="vis"></div>

    

    <
<script>
        // Vega-Lite specification
        const vegaLiteSpec = {
            "$schema": "https://vega.github.io/schema/vega-lite/v4.json",
            "title": "Bandicoots in Australia",
            "layer": [
                {
                    "data": {
                        "url": "https://raw.githubusercontent.com/Xiangjun-Xue/Bandicoot_map/main/AUS_map_v2.json",
                        "format": {"type": "json"}
                    },
                    "projection": {"type": "identity", "reflectY": true},
                    "mark": {"type": "geoshape", "stroke": "black", "strokeWidth": 1},
                    "width": 650,
                    "height": 600
                },
                {
                    "data": {
                        "url": "https://raw.githubusercontent.com/Xiangjun-Xue/Bandicoot_map/main/5120data.csv"
                    },
                    "mark": {"type": "circle", "tooltip": {"content": "data"}},
                    "encoding": {
                        "longitude": {
                            "field": "long",
                            "type": "quantitative"
                        },
                        "latitude": {
                            "field": "lat",
                            "type": "quantitative"
                        },
                        "size": {"value": 10},
                        "color": {"value": "red"}
                    }
                }
            ]
        };

        // Embed the Vega-Lite visualization into the 'vis' div
        vegaEmbed("#vis", vegaLiteSpec).then(result => {}).catch(console.error);
    </script>
</body>
</html>
