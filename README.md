# tenkipay-php
PHP Laravel code for the tenkipay webhook

#Instructions
Exclude your webhook URL for sending CRS token, for Tenkipay to post
open /app/Http/Middleware/VerifyCsrfToken.php
add your webhook url to the except array 


<code>public function tenkiPay(Request $request) \{</code>
<code>$input = $request->input();\</code>
<code>if($input['secret'] !== env('TENKIPAY_SECRET'))\{</code>
  <code>abort(403, 'Access denied');\</code>
<code>}\</code>
<code>$description = $input['description'];\</cod>
<code>$customername = $input['customer_name'];\</code>
<code>$customeremail = $input['customer_email'] ?? "";\</code>
<code>$customerphone = $input['customerphone'] ?? "";\</code>
<code>$amount = $input['amount'];\</code>
<code>// YOUR BUSINESS LOGIC HERE\</code>
<code>return response()->setStatusCode()->json;\</code>
