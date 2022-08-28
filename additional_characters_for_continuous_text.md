## Additional characters for continuous text, safe replacement
*This is an independent proposal for the inclusion of additional characters for continuous text.
Continous text is not in the scope of DIN 91379.
These characters are not recommended by DIN 91379, but the use of additional characters is allowed by this norm.*

### Allow
For continuous text the following characters from CP1252 are allowed:
|Name|Code point|Action|
|----|----------|------|
|EN DASH|2013|allow|
|EM DASH|2014|allow|
|BULLET|2022|allow|

### Allow only internally
As a safe replacement for forbidden characters the following character is allowed only internally:

|Name|Code point|Action|
|----|----------|------|
|REPLACEMENT CHARACTER|FFFD|allow internally|

### Reject or replace
Depending on the use case, rejecting or replacing illegal characters and sequences
at system boundaries may be appropriate.

The character SOFT HYPHEN must be rejected or replaced for security reasons. (See https://en.wikipedia.org/wiki/Soft_hyphen)

#### Reject at system boundaries
At system boundaries unwanted characters and sequences are rejected.
This is e.g. useful in interactive applications.
Other characters and sequences that are not explicitly allowed
are also rejected.

|Name|Code point|Action|
|----|----------|------|
|SOFT HYPHEN (SHY)|00AD |reject|
|REPLACEMENT CHARACTER|FFFD|reject|
|not allowed characters or sequences| |reject|


#### Replace
At automatic external interfaces or e.g. file upload
it may be useful to replace unwanted characters and sequences with
the Unicode REPLACEMENT CHARACTER U+FFFD.
For security reasons no other replacement character may be used.
If replacing is applied, the resulting REPLACEMENT CHARACTER U+FFFD
has to be allowed and processed correctly.


|Name|Codepoint|Replacement name|Replacement codepoint|Action|
|----|----------|---------------|---------------------|------|
|SOFT HYPHEN (SHY)|00AD |REPLACEMENT CHARACTER | FFFD |replace|
|not allowed characters or sequences| |REPLACEMENT CHARACTER | FFFD |replace|


### Delete 
For security reasons no character is deleted.
See https://unicode.org/reports/tr36/#Deletion_of_Noncharacters
