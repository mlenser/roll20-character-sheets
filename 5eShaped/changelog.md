## 8.0.0

### Breaking Changes

* Spells tab removed. The behavior on the core page with the expand option covers this need. This will save sheets with lots of spells between 10-30% of loading time, processing time, etc
* Vision, movement, and class features moved to the core page from the character page

### Features

* [#65: Honor and Sanity Attributes](https://bitbucket.org/mlenser/5eshaped/issues/65/honor-and-sanity-attributes). See screenshot below.
* The way Normal/Advantage/Disadvantage set is now changed to be more direct and require no sheet processing. There is no longer the possibility of the roll template outputting incorrect advantage state as a result of a slow script run. "Automatically revert (dis)advantage" will not work until Lucian upgrades his script. See [Automatically revert advantage needs to be updated for 8.0.0](https://github.com/symposion/roll20-shaped-scripts/issues/263)
* Normal/Advantage/Disadvantage now has 3 additional options: Query, Advantage query, and Disadvantage query. All will ask you which state to use when executing the macro. The Advantage/Disadvantage query options will default to that option.
* Initiative has the same options as above in addition to using the sheet's setting (Normal/Advantage/Disadvantage). Closes [#77: Add a CHOOSE_WHEN_ROLLING Initiative Roll Option](https://bitbucket.org/mlenser/5eshaped/issues/77/add-a-choose_when_rolling-initiative-roll)
* Skills have the same options as initiative.
* Movement is now split out into 4 different fields for PCs and NPCs. It automatically parses from the SRD and upgrades appropriately.
* Senses is now split out into 4 different fields for PCs and NPCs. It automatically parses from the SRD and upgrades appropriately.
* You can now choose a distance measurement system in the settings tag. Adjusting it will convert the numbers and labels for distances in movement and senses.
* Added class features to the Features & Traits area of the Core tab for PCs
* Features are now removed from the list of features if they are unchecked in the list of features (for example Careful spell). Closes [#76: Deactivating a feature should remove it from the list of features & traits](https://bitbucket.org/mlenser/5eshaped/issues/76/deactivating-a-feature-should-remove-it)
* Recharges have now been translated for traits, actions, reactions, etc. Old recharges have been converted for PC and NPCs. New NPCs will parse the recharge to translation. Closes [#40: Traits: short/long rest not translated](https://bitbucket.org/mlenser/5eshaped/issues/40/traits-short-long-rest-not-translated).
* Traits can now specify how many uses are used each time. Legendary Actions now specify their cost. The script will handle this via [Traits amount decremented should be based on new "used" field as of 8.0.0](https://github.com/symposion/roll20-shaped-scripts/issues/265). Closes [#7: Trait and Legendary cost support](https://bitbucket.org/mlenser/5eshaped/issues/7/trait-and-legendary-cost-support)
* Size for PCs moved to the header next to race.

![alt text](http://i.imgur.com/7u7sJDI.png "Honor and Sanity")


### Bug Fixes

* Structural change to how I access multiple repeating sections that should make them much quicker (I get all the values and then set them all at once instead of setting them individually)
* Large cleanup around spells as a result of the above and other minor changes that should speed up their processing. Same with psionics.
* Structural change to how I verify that the data I'm sending isn't already on the server (if it was blank and is being sent as blank it won't be sent now)
* Cleanup around other areas like abilities, ability checks, skills, saving throws, etc to speed them up a little bit.
* Ability checks and Saving throws macros are now generated in a more maintainable way. Both the chat macro and the query macro are visible on the page now.
* [#68: Spell duplication on script import of spellcasting monsters](https://bitbucket.org/mlenser/5eshaped/issues/68/spell-duplication-on-script-import-of). When parsing spells from the traits section it will check to see if each spell exists. If a spell by that name exists then it will not create a new one.
* [#74: Coin weight](https://bitbucket.org/mlenser/5eshaped/issues/74/coin-weight)
