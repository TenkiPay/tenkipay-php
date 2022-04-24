# tenkipay-php
PHP Laravel code for the tenkipay webhook

# Instructions
Exclude your webhook URL for sending CRS token, for Tenkipay to post
open <code>/app/Http/Middleware/VerifyCsrfToken.php</code>
add your webhook url to the except array 

configure your webhook url on tenkipay 
add your webhook secret to .env
TENKIPAY_SECRET="{your webhook secret}"


```public function tenkiPay(Request $request){</code>
   $input = $request->input();
   if($input['secret'] !== env('TENKIPAY_SECRET'))
      abort(403, 'Access denied');
   }
   $description = $input['description'];
   $customername = $input['customer_name'];
   $customeremail = $input['customer_email'] ?? "";
   $customerphone = $input['customerphone'] ?? "";
   $amount = $input['amount'];
   // YOUR BUSINESS LOGIC HERE
   return response()->setStatusCode()->json;
   ```
