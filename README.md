# MarkdownHelper

<kbd>
  <img src="/images/include.png" width="50">
</kbd>

This helper enables file inclusion in GitHub markdown.

You can use it to merge external files into a markdown (```.md```) file.

The merged text can be highlighted in a code block:

<code>include.rb</code>
```ruby
class RubyCode
  def initialize
    raise RuntimeError.new('I am only an example!')
  end
end
```

or plain in a code block:

<code>include.rb</code>
```
class RubyCode
  def initialize
    raise RuntimeError.new('I am only an example!')
  end
end
```

or verbatim (which GitHub renders however it likes).

## Usage

### Including Files in Markdown

<code>include.md</code>
```verbatim
# Include as highlighted code block.

@[ruby](include.rb)

# Include as plain code block.

@[:code_block](include.rb)

# Include verbatim.

@[:verbatim](include.rb)
```

Each inclusion line:

* Starts with ```@```.
* Has a *treatment* in square brackets, one of:
  * A language name such as ```ruby'``, to include a highlighted code block.
  * ```:code_block```, to include a plain code block.
  * ```:verbatim```, to include text verbatim (to be rendered as markdown).
* Has a relative file path in parentheses, pointing to the file to be included.

### Including the Files

<code>usage.rb</code>
```ruby
require 'markdown_helper'

markdown_helper = MarkdownHelper.new
template_file_path = 'highlight_ruby_template.md'
markdown_file_path = 'highlighted_ruby.rb'
markdown_helper.include(template_file_path, markdown_file_path)
```
