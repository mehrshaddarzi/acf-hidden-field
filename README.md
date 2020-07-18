### Hidden Field For ACF (Advanced Custom Fields) WordPress Plugin

![Hidden Field in ACF](https://raw.githubusercontent.com/mehrshaddarzi/acf-hidden-field/master/screenshot.jpg)

for Use Custom JavaScript Action in Input, use `acf_hidden_field_custom_script` action:

```php
add_action('acf_hidden_field_custom_script', 'add_default_value');
function add_default_value($field) {
            ?>
            <script>
                jQuery(document).ready(function ($) {
                    /**
                     * https://www.advancedcustomfields.com/resources/javascript-api/
                     */
                    acf.addAction('load', function () {
                        let input = $("#acf-<?php echo $field['key']; ?>");
                        if (input.val().length < 1) {
                            input.val("a new value");
                        }
                    });
                });
            </script>
            <?php
});
```

