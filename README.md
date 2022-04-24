# tenkipay-php
PHP Laravel code for the tenkipay webhook

#Instructions
Exclude your webhook URL for sending CRS token, for Tenkipay to post
open /app/Http/Middleware/VerifyCsrfToken.php
add your webhook url to the except array 


<code>public function tenkiPay(Request $request){space}{space}{</code>
<code>$input = $request->input();{space}{space}</code>
<code>if($input['secret'] !== env('TENKIPAY_SECRET')){space}{space}{</code>
  <code>abort(403, 'Access denied');{space}{space}</code>
<code>}\</code>
<code>$description = $input['description'];{space}{space}</cod>
<code>$customername = $input['customer_name'];{space}{space}</code>
<code>$customeremail = $input['customer_email'] ?? "";{space}{space}</code>
<code>$customerphone = $input['customerphone'] ?? "";{space}{space}</code>
<code>$amount = $input['amount'];{space}{space}</code>
<code>// YOUR BUSINESS LOGIC HERE{space}{space}</code>
<code>return response()->setStatusCode()->json;{space}{space}</code>
