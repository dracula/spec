Dracula Syntax Highlighting Specification
----

# Prelude

## Interpreting this specification

Language syntaxes and scopes will be referred to in the following manner throughout this document:

ScopeOfInterest : ( ForegroundColor, BackgroundColor? ) Italic? Bold?

NOTE: Throughout the document, broad ranges of syntax tokens will be referred to using [TextMate Naming Conventions](http://manual.macromates.com/en/language_grammars#naming_conventions)

## Color Palette

### Standard

Background : #282A36

Foreground : #F8F8F2

Selection  : #44475A

Comment    : #6272A4

Red        : #FF5555

Orange     : #FFB86C

Yellow     : #F4F99D

Green      : #50FA7B

Purple     : #BD93F9

Cyan       : #8BE9FD

Pink       : #FF79C6

### ANSI

AnsiBlack          : #4D4D4D

AnsiRed            : #FF5555

AnsiGreen          : #50FA7B

AnsiYellow         : #F1FA8C

AnsiBlue           : #BD93F9

AnsiMagenta        : #FF79C6

AnsiCyan           : #8BE9FD

AnsiWhite          : #BFBFBF

AnsiBrightBlack   : #575757

AnsiBrightRed     : #FF6E67

AnsiBrightGreen   : #5AF78E

AnsiBrightYellow  : #F4F99D

AnsiBrightBlue    : #CAA9FA

AnsiBrightMagenta : #FF92D0

AnsiBrightCyan    : #9AEDFE

AnsiBrightWhite   : #F8F8F2

## Example spec-compliant theme implementation

A fully spec-compliant theme implementation can be found by visiting the [dracula/visual-studio-code](https://github.com/dracula/visual-studio-code/) repository.

# General

Invalid: ( Foreground, Red )

Deprecated: ( Foreground, Purple )

Error: ( Red )

## Diffs

DiffText: ( Comment )

DiffHeader: ( Comment )

DiffInserted: ( Green )

DiffDeleted: ( Red )

DiffChanged: ( Orange )

## Markup (Markdown, RST, etc.)

MarkupBold: ( Orange ) Bold

MarkupHeading: ( Purple ) Bold

MarkupItalic: ( Yellow ) Italic

MarkupListBulletOrNumber: ( Cyan )

MarkupInlineCode: ( Green )

MarkupLinkUrl: ( Cyan )

MarkupLinkText: ( Pink )

MarkupBlockquote: ( Yellow ) Italic

MarkupHorizontalRule: ( Comment )

MarkupCodeBlockWithoutSyntax: ( Orange )

MarkupRSTConstants: ( Purple)

NOTE: Braces and parens should be the same color as the foreground color of the currently scoped position in the document (e.g. {Purple} for headings, {Foreground} for regular text)

# Classes

ClassName: ( Cyan )

InstanceReservedWords: ( Purple ) Italic

NOTE: {InstanceReservedWords} refers to reserved words that the language uses to interact with the instance (e.g. `this`, `self`, `super`).

InheritedClassName: ( Cyan ) Italic

# Comments

Comment: ( Comment )

DocCommentKeywords: ( Cyan ) Italic

DocCommentParameters: ( Orange ) Italic

# Constants

Constant: ( Purple )

ConstantEscapeSequences: ( Pink )

# Entities

HtmlTags: ( Pink )

CssParentSelectors: ( Pink )

HtmlCssAttributeNames: ( Green )

# Functions/Methods

FunctionNames: ( Green )

FunctionParameters: ( Orange ) Italic

Decorators: ( Green ) Italic

# Keywords

Keyword: ( Pink )

KeywordNew: ( Pink ) Bold

KeywordGenericCssSelector: ( Pink )

# Language Built-ins

Support: ( Cyan ) Italic

BuiltInMagicMethodsOrConstants: ( Purple )

BuiltInFunctions: ( Cyan )

# Punctuation

SeparatorsReferencesOrAccessors: ( Pink )

NOTE: {SeparatorsReferencesOrAccessors} does not refer to simple object or class {dot} accessors.

BracketsParensBraces: ( Foreground )

StringInterpolationOperators: ( Pink )

# Serializable / Configuration Languages

Keys: ( Cyan )

DateTime: ( Orange )

YamlAliases: ( Green ) Italic Underline

# Storage

Storage: ( Pink )

Types: ( Cyan ) Italic

Modifiers: ( Pink )

GenericTemplatesAndMappedDeclarations: ( Orange ) Italic

NOTE: {GenericTemplatesAndMappedDeclarations} refers to the declarations of generic types only. In the following example, only the `T` in the brackets would be {Orange}. `function myFunc<T>(x: T): T {}`

NOTE: {GenericTemplatesAndMappedDeclarations} would also color `P` and `T` on the LHS and `T` in the declaration of the following expression.

**Example**

```ts
type PartialExample<T> = { // T = Orange Italic
  [P in keyof T]?: T[P];   // P and T on the LHS = Orange Italic
}
```

# Strings

String: ( Yellow )

StringRegExp: ( Red )

# Variables

Variable: ( Foreground )

ObjectKeys: ( Foreground )

DestructuringAliasLHS: ( Orange ) Italic

DestructureingAliasRHS: ( Foregroud )

**Destructuring Example**

```ts
const x = {
    foo: 'foo',
    bar: 'bar',
    baz: 'baz',
};

// foo = Orange Italic
// myFoo = Foreground
const { foo: myFoo } = x;
```

**Import/Export Example**

```ts
export { Foo };                     // Foo = Foreground
export { Foo as myFoo };            // Foo = Orange Italic, myFoo = Foreground
import { Foo as myFoo } from 'foo'; // Foo = Orange Italic, myFoo = Foreground
import { Foo } from 'foo';          // Foo = Foreground
```


