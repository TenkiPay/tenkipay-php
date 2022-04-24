# tenkipay-php
PHP Laravel code for the tenkipay webhook
<code>public function tenkiPay(Request $request) {
$input = $request->input();
if($input['secret'] !== env('TENKIPAY_PUBLIC')){
  abort(403, 'Access denied');

}
$description = $input['description'];
$customername = $input['customer_name'];
$customeremail = $input['customer_email'] ?? "";
$customerphone = $input['customerphone'] ?? "";
$amount = $input['amount'];

// YOUR BUSNESS LOGIC HERE
rreturn response()->setStatusCode()->json;</code>
