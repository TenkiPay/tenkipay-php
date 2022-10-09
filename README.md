# tenkipay-php
PHP Laravel tenkipay webhook integration

# Instructions
Create a webhook controller
<code> php artisan make:controller Webhook
Exclude your webhook URL for sending CRS token, for Tenkipay to post
open <code>/app/Http/Middleware/VerifyCsrfToken.php</code>
add your webhook url to the except array 
<code>
   protected $except = [
        //
        'api/webhook',
    ];
 </code>

configure your webhook url on tenkipay 
add your webhook secret to .env
TENKIPAY_SECRET="{your webhook secret}"
Open the <code>app/Https/Controllers/Webhook.php</code> and add the tenkipay method in the Webhook class

```public function tenkiPay(Request $request){</code>
      $input = $request->input();
      if($input['secret'] !== env('TENKIPAY_SECRET')){
         abort(403, 'Access denied');
      }
      $description = $input['description'];
      $customername = $input['customer_name'];
      $customeremail = $input['customer_email'] ?? "";
      $customerphone = $input['customerphone'] ?? "";
      $amount = $input['amount'];
      // YOUR BUSINESS LOGIC HERE
      return response()->setStatusCode()->json;
    }
   ```
