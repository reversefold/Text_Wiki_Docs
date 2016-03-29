

*  Constructor
    * [Text_Wiki()](MethodTextWiki) -- instantiates a new Text_Wiki object

*  Parse and render
    * [transform()](MethodTransform) -- Parses text and returns in a rendered format
    * [parse()](MethodParse) -- Parses text according to rules and tokenizes the source
    * [render()](MethodRender) -- Renders parsed source text into an output format

*  Rule-set management
    * [insertRule()](MethodInsertRule) -- Adds a rule to the set
    * [deleteRule()](MethodDeleteRule) -- Removes a rule from the set
    * [changeRule()](MethodChangeRule) -- Changes from one rule to another in place within the set
    * [enableRule()](MethodEnableRule) -- Enables a rule in-place
    * [disableRule()](MethodDisableRule) -- Disables a rule in-place

*  Configuration management
    * Parse
      * [setParseConf()](MethodSetParseConf) -- Sets the configuration for a parse rule
      * [getParseConf()](MethodGetParseConf) -- Gets the configuration for a parse rule
    * Format
      * [setFormatConf()](MethodSetFormatConf) -- Sets the configuration for how a format is pre- and post-rendered
      * [getFormatConf()](MethodGetFormatConf) -- Gets the configuration for how a format is pre- and post-rendered
    * Render
      * [setRenderConf()](MethodSetRenderConf) -- Sets the configuration for how a rule is in rendered in a specific format
      * [getRenderConf()](MethodGetRenderConf) -- Gets the configuration for how a rule is in rendered in a specific format

*  Path management for user-defined rules
    * [addPath()](MethodAddPath) -- Adds a directory to the path for user-defined parse, format, or render classes
    * [getPath()](MethodGetPath) -- Gets the path directories for user-defined parse, format, or render classes

*  Other methods
    * [getSource()](MethodGetSource) -- Gets the parsed source text with delimited token markers
    * [getTokens()](MethodGetTokens) -- Gets the tokens parsed out of the source text
