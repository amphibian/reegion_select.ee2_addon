REEgion Select is an EE2 plugin and fieldtype that displays a list of:

- countries (based on the ISO 3166-1 list of countries, dependent territories, and special areas of geographical interest)
- US states (based on the USPS official list of US states and possessions)
- Canadian provinces and territories
- UK counties
- Australian states and territories
- South African provinces
- Canadian provinces and U.S. states together (or U.S. States and Canadian provinces together)
- All of the above sub-country regions together

##Fieldtype Usage

To use the fieldtype, simply install and then choose REEgion Select from the fieldtype menu when creating a new custom field (or Matrix field), then choose which kind of regions you'd like to display.

In your templates, display your custom field using `{field_name:name}` (or simply `{field_name}`) to display the name of the region (i.e., United States); `{field_name:alpha2}` to display the ISO 3166-2 code for the country, state, or province (i.e., US); or use `{field_name:alpha3}` to display the ISO 3166-1 code for the country (i.e., USA).

##Plugin Usage

Use the following EE tags to generate each type of dropdown `<select>` menu in your templates:

`{exp:reegion_select:countries}`

`{exp:reegion_select:states}`

`{exp:reegion_select:provinces}`

`{exp:reegion_select:ukcounties}`

`{exp:reegion_select:provinces_states}`

`{exp:reegion_select:states_provinces}`

`{exp:reegion_select:au_states}`

`{exp:reegion_select:za_provinces}`

`{exp:reegion_select:all}`

Or use a tag pair to generate your own custom lists or menus, using the following variables:

	{exp:reegion_select:countries}
		{region_name}
		{region_alpha2}
		{region_alpha3}
		{count}
		{total_results}
	{/exp:reegion_select:countries}

(And likewise for the other region types.)

##Plugin Parameters

REEgion Select accepts ten optional parameters:

- `show=""` -- A pipe-delimited list of values to show, if you don't want all of the default values to display. (e.g., `show="CA|NY|OH|MI"`)
- `hide=""` -- A pipe-delimited list of values to hide, if you don't want all of the default values to display. (e.g., `hide="Canada|United States|Mexico"`)
- `name=""` -- Value for the "name" attribute of the `<select>` menu. Defaults: "country", "state", "province", "county", "province_state".
- `type=""` -- `alpha2` will use use the ISO 3166-2 abbreviation as the <option> value for countries, states, and provinces. `alpha3` will use use the ISO 3166-1 abbreviation as the <option> value for countries. "name" will use the region name as the value. Default: `name`.
- `selected=""` -- Value of the <option> element that should be selected by default.
- `title=""` -- A title or heading for the `<select>` menu. Defaults to "Select a (Country/State/Province/etc)".
- `id=""` -- Value for the `id` attribute of the `<select>` menu.
- `class=""` -- Value for the `class` attribute of the `<select>` menu. Defaults to `reegion_select`.
- `tabindex=""` -- Value for the `tabindex` attribute of the `<select>` menu.
- `required=""` -- whether to add the HTML5 "required" attribute to the `<select>` menu.
- `data-[value]=""` -- any "data-" values passed as individual parameters will be added verbatim to the `<select>` menu.
- `null_divider="n"` -- Whether or not to include a divider option with a null value at the top of the menu. Defaults to `y`.

## Low Variables Usage

REEgion Select can also be used as a var type in the [Low Variables](http://devot-ee.com/add-ons/low-variables/) module. The resulting global variables will output the ISO 3166-2 abbreviation value for your region, but you can access the "name" or "alpha3" values by using the `{exp:low_variables:parse}` tag:

`{exp:low_variables:parse var="var_name" type="name"}`

`{exp:low_variables:parse var="var_name" type="alpha3"}`

##Compatibility

This version of REEgion Select is only compatible with ExpressionEngine 2.1.3 or higher. The ExpressionEngine 1.6-compatible version [can be found here](http://github.com/amphibian/pi.reegion_select.ee_addon). REEgion Select can also be used as a [Low Variables](http://devot-ee.com/add-ons/low-variables/) var type, and REEgion Select fields are optimized for [Low Search](http://devot-ee.com/add-ons/low-search/) indexing.