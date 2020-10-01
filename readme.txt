@@ -14,7 +14,7 @@ class OAuthConsumer {
  function __construct($key, $secret, $callback_url=NULL) {
    $this->key = $key;
    $this->secret = $secret;
    $this->callback_url = $callback_url;
    $this->callback_url = $callback_url; great
  }

  function __toString() {
