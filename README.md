# Action after confirm payment on Wocommerce
Snippet to start specific function after payment is confirmed on Woocommerce. In this example, after payment is comfirmed set the new value to user.

```
function checkPayment ($order_id) {
    
    ///get the order
    $order = new WC_Order($order_id);
    $user_id = $order->get_user_id();

    ///check for set info
    update_user_meta( $user_id, 'field_name', 'field_value' );
    
}

add_action( 'woocommerce_payment_complete', 'checkPayment' );
```

## Important
This Snippet requires the payment method to call woocommerce_payment_complete() / $order->payment_complete(). Most payment methods do this already because is default on woocommerce payment method.
