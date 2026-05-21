<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invoice - Get Extra Hands</title>
    <!-- Tailwind CSS for modern responsive styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for premium typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* Stripe's cool light gray background */
        }
        /* Stripe-like focus ring */
        input:focus, textarea:focus {
            outline: none;
            border-color: #635bff;
            box-shadow: 0 0 0 3px rgba(99, 91, 255, 0.15);
        }
        /* Printable styling */
        @media print {
            body {
                background-color: white !important;
                padding: 0 !important;
            }
            .no-print {
                display: none !important;
            }
            .print-card {
                box-shadow: none !important;
                border: none !important;
                padding: 0 !important;
                margin: 0 !important;
                max-width: 100% !important;
                width: 100% !important;
            }
        }
    </style>
</head>
<body class="text-slate-800 antialiased min-h-screen py-6 md:py-12 px-4 flex flex-col items-center">

    <!-- Print Action Header (Hidden on print) -->
    <div class="w-full max-w-3xl mb-6 flex justify-end no-print">
        <button onclick="window.print()" class="px-4 py-2.5 text-sm font-semibold text-slate-700 bg-white border border-slate-200 rounded-xl hover:bg-slate-50 hover:border-slate-300 transition-all flex items-center gap-2 shadow-sm">
            <svg class="w-4 h-4 text-slate-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 17h2a2 2 0 002-2v-4a2 2 0 00-2-2H5a2 2 0 00-2 2v4a2 2 0 00-2 2h2m2 4h10a2 2 0 002-2v-4a2 2 0 00-2-2H9a2 2 0 00-2 2v4a2 2 0 002 2zm8-12V5a2 2 0 00-2-2H9a2 2 0 00-2 2v4h10z"></path>
            </svg>
            Print or Save PDF
        </button>
    </div>

    <!-- Main Invoice Card (Centered & Clean) -->
    <div class="w-full max-w-3xl bg-white rounded-2xl border border-slate-200 shadow-[0_4px_12px_rgba(0,0,0,0.02),0_1px_2px_rgba(0,0,0,0.02)] print-card overflow-hidden">
        
        <!-- Invoice Content Container -->
        <div class="p-6 md:p-12">
            
            <!-- Header Section -->
            <div class="flex flex-col md:flex-row justify-between items-start gap-6 border-b border-slate-100 pb-8">
                
                <!-- Left Side: Company Logo & Details -->
                <div class="space-y-4">
                    <div class="flex items-center gap-4">
                        <div id="logo-container" class="w-16 h-16 bg-white rounded-xl border border-slate-100 flex items-center justify-center">
                            <img id="logo-preview" class="w-full h-full object-contain rounded-xl p-1" src="https://res.cloudinary.com/dwmsgnm4p/image/upload/q_auto/f_auto/v1779386601/GEHLOGO_zrvacq.png" alt="Get Extra Hands Logo">
                        </div>
                        <div>
                            <h1 class="text-xl font-bold tracking-tight text-slate-900">Get Extra Hands</h1>
                            <p class="text-xs font-semibold uppercase tracking-wider text-[#635bff]">Professional Cleaning</p>
                        </div>
                    </div>
                    
                    <!-- Contact Details -->
                    <div class="text-[13px] text-slate-500 space-y-1">
                        <div class="flex items-center gap-2">
                            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>
                            <a href="mailto:team@getextrahands.com" class="hover:text-slate-900 transition-colors">team@getextrahands.com</a>
                        </div>
                        <div class="flex items-center gap-2">
                            <svg class="w-4 h-4 text-slate-400" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.94.725l.548 2.2a1 1 0 01-.321.988l-1.305.98a10.582 10.582 0 004.872 4.872l.98-1.305a1 1 0 01.988-.321l2.2.548a1 1 0 01.725.94V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path></svg>
                            <a href="tel:3019660803" class="hover:text-slate-900 transition-colors">301-966-0803</a>
                        </div>
                    </div>
                </div>

                <!-- Right Side: Invoice Meta -->
                <div class="w-full md:w-auto text-left md:text-right space-y-1.5 self-stretch flex flex-col justify-between">
                    <div>
                        <span class="text-xs font-semibold tracking-wider text-slate-400 uppercase">Invoice</span>
                        <div class="flex items-center justify-start md:justify-end gap-1 text-2xl font-semibold text-slate-900">
                            <span>#</span>
                            <input type="text" class="w-24 border-b border-transparent hover:border-slate-200 focus:border-[#635bff] bg-transparent py-0 px-1 font-semibold text-slate-900 text-left md:text-right" value="10045">
                        </div>
                    </div>
                    <div class="text-[13px] text-slate-500 space-y-1 mt-4 md:mt-0">
                        <div class="flex md:justify-end gap-4">
                            <span class="text-slate-400">Date issued</span>
                            <input type="date" class="border-b border-transparent hover:border-slate-200 focus:border-[#635bff] bg-transparent py-0 px-1 text-slate-700 text-left md:text-right font-medium" id="issue-date">
                        </div>
                        <div class="flex md:justify-end gap-4">
                            <span class="text-slate-400">Due date</span>
                            <input type="date" class="border-b border-transparent hover:border-slate-200 focus:border-[#635bff] bg-transparent py-0 px-1 text-slate-700 text-left md:text-right font-medium" id="due-date">
                        </div>
                    </div>
                </div>
            </div>

            <!-- Billing Info Section -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 py-8 border-b border-slate-100">
                <div>
                    <span class="text-xs font-semibold tracking-wider text-slate-400 uppercase block mb-3">Bill to</span>
                    <input type="text" class="w-full text-base font-semibold text-slate-800 bg-transparent border-b border-transparent hover:border-slate-200 focus:border-[#635bff] py-0.5 px-1" value="Leslie Islar">
                    
                    <div class="text-sm text-slate-500 mt-1 space-y-0.5 px-1">
                        <div>soulcolethebrand@gmail.com</div>
                        <div>(301) 602-2697</div>
                        <textarea class="w-full text-sm text-slate-500 bg-transparent border-b border-transparent hover:border-slate-200 focus:border-[#635bff] py-1 mt-1 h-20 resize-none" placeholder="Billing Address">301 Tingey Street SE
PH28
DC 20003 US</textarea>
                    </div>
                </div>
                <div class="md:text-right flex flex-col justify-start space-y-1">
                    <span class="text-xs font-semibold tracking-wider text-slate-400 uppercase block mb-2">Service details</span>
                    <p class="text-sm font-semibold text-slate-800">2 Bed, 2.5 Bath, 2-Level Property</p>
                    <p class="text-xs text-slate-500">Comprehensive Top-to-Bottom Deep Clean</p>
                    
                    <!-- Added Service Date & ETA Details -->
                    <div class="pt-3 border-t border-slate-50 mt-3 space-y-1 text-sm text-slate-600">
                        <div><strong class="text-slate-800 font-medium">Service Date:</strong> 6/9/26</div>
                        <div><strong class="text-slate-800 font-medium">ETA:</strong> 7:00 AM - 8:00 AM</div>
                    </div>
                </div>
            </div>

            <!-- Invoice Line Items Table -->
            <div class="py-8">
                <table class="w-full text-left">
                    <thead>
                        <tr class="border-b border-slate-200 text-xs font-semibold tracking-wider text-slate-400 uppercase">
                            <th class="pb-3 font-semibold">Description</th>
                            <th class="pb-3 text-right font-semibold w-16">Qty</th>
                            <th class="pb-3 text-right font-semibold w-24">Price</th>
                            <th class="pb-3 text-right font-semibold w-24">Amount</th>
                        </tr>
                    </thead>
                    <tbody class="divide-y divide-slate-100 text-sm text-slate-700">
                        <!-- Standard Package -->
                        <tr>
                            <td class="py-5 pr-4">
                                <span class="font-semibold text-slate-900 block">Deep Cleaning Package Base</span>
                                <span class="text-xs text-slate-500 mt-0.5 block max-w-lg">
                                    Comprehensive top-to-bottom sanitize of both levels. Includes thorough vacuuming of all rooms/stairs, deep dusting, baseboard detailing, sanitization of 2.5 bathrooms, and hard floor scrubbing/mopping.
                                </span>
                            </td>
                            <td class="py-5 text-right font-medium">1</td>
                            <td class="py-5 text-right font-medium">$270.00</td>
                            <td class="py-5 text-right font-semibold text-slate-900">$270.00</td>
                        </tr>
                        <!-- Inside Oven -->
                        <tr>
                            <td class="py-5 pr-4">
                                <span class="font-semibold text-slate-900 block">Add-on: Inside Oven Deep Clean</span>
                                <span class="text-xs text-slate-500 mt-0.5 block max-w-lg">
                                    Thorough interior oven degreasing, baking rack scrub, window scrape, and polishing.
                                </span>
                            </td>
                            <td class="py-5 text-right font-medium">1</td>
                            <td class="py-5 text-right font-medium">$60.00</td>
                            <td class="py-5 text-right font-semibold text-slate-900">$60.00</td>
                        </tr>
                        <!-- Inside Fridge -->
                        <tr>
                            <td class="py-5 pr-4">
                                <span class="font-semibold text-slate-900 block">Add-on: Inside Refrigerator Deep Clean</span>
                                <span class="text-xs text-slate-500 mt-0.5 block max-w-lg">
                                    Detailed sanitization of interior shelves, door guards, drawers, and cooling components.
                                </span>
                            </td>
                            <td class="py-5 text-right font-medium">1</td>
                            <td class="py-5 text-right font-medium">$60.00</td>
                            <td class="py-5 text-right font-semibold text-slate-900">$60.00</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <!-- Financial Totals Block -->
            <div class="flex justify-end border-t border-slate-100 pt-6">
                <div class="w-full md:w-80 space-y-3 text-sm">
                    <div class="flex justify-between text-slate-500">
                        <span>Subtotal</span>
                        <span class="font-medium">$390.00</span>
                    </div>
                    <div class="flex justify-between text-emerald-600 font-medium">
                        <span>Promo Discount (maypeace)</span>
                        <span>-$50.00</span>
                    </div>
                    <div class="flex justify-between text-slate-500">
                        <span>Tax (0%)</span>
                        <span class="font-medium">$0.00</span>
                    </div>
                    <div class="flex justify-between text-slate-900 pt-3 border-t border-slate-100">
                        <span class="font-bold text-slate-900 text-base">Total due</span>
                        <span class="font-bold text-xl text-[#635bff]" id="final-total">$340.00</span>
                    </div>
                </div>
            </div>

            <!-- Professional Footer -->
            <div class="border-t border-slate-100 mt-12 pt-6 text-center md:text-left">
                <h4 class="text-xs font-semibold tracking-wider text-slate-400 uppercase mb-2">Notes & Payment</h4>
                <p class="text-xs text-slate-500 leading-relaxed max-w-xl">
                    Thank you for choosing Get Extra Hands! Please note that as part of this exclusive promotion, we are strictly accepting payments via <strong>Cash App</strong> or <strong>Apple Pay</strong>. Please use reference code <strong>240517 6333 GEH/Getextrahands</strong> when completing your payment.
                </p>
                
                <!-- Payment badge detail -->
                <div class="mt-6 pt-4 border-t border-slate-100/60 flex flex-wrap justify-between items-center gap-4 text-xs text-slate-400">
                    <span class="flex items-center gap-1.5">
                        <svg class="w-4 h-4 text-emerald-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                        Secure Digital Invoicing
                    </span>
                    <span>Get Extra Hands LLC &bull; team@getextrahands.com</span>
                </div>
            </div>

        </div>
    </div>

    <script>
        // Set dates automatically
        document.addEventListener('DOMContentLoaded', () => {
            const today = new Date();
            const formattedToday = today.toISOString().split('T')[0];
            
            document.getElementById('issue-date').value = formattedToday;
            document.getElementById('due-date').value = formattedToday; // Due upon receipt
        });
    </script>
</body>
</html>
