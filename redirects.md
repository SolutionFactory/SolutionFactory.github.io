---
title: Redirects - Solution Factory
---

# Redirects

Easily setup redirects for your WordPress site.

## Usage

After activating the plugin go to the plugin's settings page:

![Settings menu](/images/redirects-settings-menu.png)

Click on the "Add new" button to create a new redirect rule.

After adding a new redirect rule an empty rule is added to the table. Each rule has 6 columns: active, pattern, from, to, type and remove.

### Active

Check to make the rule active, meaning it will be used when trying to rewrite requests

### Pattern

The pattern describe in what way we want to match the original URL. There are four different possible patterns to choose from: Starts with, Ends with, Equals and Regex.

![Settings page](/images/redirects-settings-page.png)

**Starts with**

If the originating URL starts with the following string it will match and be redirected, e.g.:

    http://yourdomain.com/this/is/the/old/url

In the above example if we use the "Starts with" pattern and use `/this/is` as the "From" URL it will match the request and the page will be redirected. We could have also used for example: `/this`, `/th`, `/this/is/the/old` or any string which is at the start of our URL.

**Ends with**

If the originating URL ends with the following string it will match and be redirected, e.g.:

    http://yourdomain.com/this/is/the/old/url

In the above example if we use the "Ends with" pattern and use `/url` as the "From" URL it will match the request and the page will be redirected. We could have also used for example: `url`, `/old/url or any string which is at the end of our URL.

**Equals**

This pattern will only match when the path (e.g. `/this/is/the/old/url`) *exactly* matches the current URL. This means that the following URL will match:

    http://yourdomain.com/this/is/the/old/url

But these don't:

    http://yourdomain.com/xthis/is/the/old/url
    http://yourdomain.com/this/is/the/old/urlx
    http://yourdomain.com/completely-different

**Regex**

This pattern allows you to match URLs based on PCRE regex patterns. The actual regex pattern should always include delimiters, because behind the scenes the pattern is used in PHP's [`preg_match`](http://php.net/manual/en/function.preg-match.php) function.

### From

The original URL to be redirected. Note that these URLs should only contain relative paths (with the protocol and domainname) e.g.:

    /some/path/file.html

### To

The URL to redirect to.

### Type

The type of the redirect. Usually this will either be a `301` (Moved permanently) or a `302` (Temporary redirect) redirect.

*Note: the often used 302 redirect has been superseded by 303 and 307 redirects.*

For more information see the [Wikipedia page](http://en.wikipedia.org/wiki/URL_redirection) about URL redirection.

### Remove

Click this link to completely remove a redirect rule

## Sorting

To sort the redirect rules simply drag and drop a rule and click "Save Changes".

![Sorting](/images/redirects-settings-page-sort.png)

## Filtering

To filter the list of redirect rules (useful when you have a lot of rules and you want to find specific ones) simply enter a string you want to filter on and click "Filter". The list of redirect rules will be filtered to only show the rules which containing the text you entered in the filter. The filter will filter based on the "From" and "To" fields. If any of those two fields contain your filter text the rule will not be filtered out.

![Filtering](/images/redirects-settings-page-filter.png)
