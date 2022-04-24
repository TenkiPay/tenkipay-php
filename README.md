# tenkipay-php
PHP Laravel code for the tenkipay webhook

#Instructions
Exclude your webhook URL for sending CRS token, for Tenkipay to post
open /app/Http/Middleware/VerifyCsrfToken.php
add your webhook url to the except array 


<code>public function tenkiPay(Request $request){</code>{space}{space}
<code>$input = $request->input();</code>{space}{space}
<code>if($input['secret'] !== env('TENKIPAY_SECRET')){</code>{space}{space}
  <code>abort(403, 'Access denied');</code>{space}{space}
<code>}</code>{space}{space}
<code>$description = $input['description'];</cod>{space}{space}
<code>$customername = $input['customer_name'];</code>{space}{space}
<code>$customeremail = $input['customer_email'] ?? "";</code>{space}{space}
<code>$customerphone = $input['customerphone'] ?? "";</code>{space}{space}
<code>$amount = $input['amount'];</code>{space}{space}
<code>// YOUR BUSINESS LOGIC HERE</code>{space}{space}
<code>return response()->setStatusCode()->json;</code>
