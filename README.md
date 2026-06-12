# GaeaMinecraftWorldgen
A Gaea large-world generator based on Minecraft's worldgen logic

https://github.com/user-attachments/assets/ea24368c-a347-434f-986c-9293a58f8517


Based on Minecraft's (old?) world generation: https://minecraft.wiki/w/World_generation, https://www.youtube.com/watch?v=CSa5O6knuwI

The main contient generation is based on three noise maps: continentalness, erosion, and weirdness. These are run through curves to shape them, weirdness is run through a function to generate a 'peaks and valleys' map and these added together to form a base heightmap (continentalness + erosion + peaksandvalleys, each scaled down proportionally and normalized). Continentalness is given an edge so that land is unlikely to reach the edge of the map and there should always be an ocean border. 

Biomes are driven by two noise maps: temperature and humidity. I don't mask them into defined biomes like Minecraft does, I just use it for coloring and to drive hydraulic/thermal erosion. Both are masked by the ocean which has average values for both, so temperature and humidity extremes will be higher inland than on the coasts. I also use a Sunlight node to simulate ocean winds, so islands will have a 'dry' and 'wet' side. Beaches have a lot of manual tweaking to work well in a 4km game map, but are too large and flat. 

By randomizing these noise maps, you can generate an endless variety of world maps. 

This is provided as a basic proof-of-concept for Gaea large world generation, and still needs a lot of work to be able to generate game-ready worlds. If I continue to work on this in the future, the next major feature would be to generate biome masks to drive landscape painting and PCG in game engines like Unreal Engine.
