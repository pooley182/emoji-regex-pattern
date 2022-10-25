# emoji-regex-pattern

This package for PHP builds a regex pattern that will match any emojis as defined by the Unicode consortium.
It's especially useful when validating user submitted data if you want to remove emojis to sanitise your data.

## versioning

This package does not follow typical symantic versioning rules. Typical version numbering would follow the convention X.Y.Z where X is a major version which denotes breaking changes in the package, Y would be a minor version that introduces new features but doesn't break anything, and Z would be a patch version that fixes up some code without any major changes or new features.

The version numbers of this package follow the versioning numbers of the Unicode Consortiums Emojis. V14.0 of this package will match all emojis within the consortiums V14.0 Emoji set. V15.0 of this package matches the consortiums V15.0 set of emojis. etc.

Therefore we recommend installing this package with `composer require pooley182/emoji-regex-pattern ">=14.0.2"`, this will mean that as new emoji character sets are released your composer package will be updated to match them.

## How to use

### Install

```shell
composer require pooley182/emoji-regex-pattern ">=14.0.2"
```

### Usage

```php
use Pooley182\EmojiRegexPattern\EmojiRegexPattern;

private function hasEmojis($string) {
    $emojiRegexPattern = '/'.EmojiRegexPattern::getEmojiPattern().'/u';

    preg_match($emojiRegexPattern, $string, $matches);

    return !empty($matches);
}
