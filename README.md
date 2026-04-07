<!DOCTYPE html>
<html lang="sv">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Säker Checkout | Din Butik</title>
    <style>
        :root {
            --primary-color: #2563eb;
            --bg-color: #f3f4f6;
            --text-main: #1f2937;
            --success-green: #10b981;
        }

        body {
            font-family: 'Inter', -apple-system, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
        }

        .checkout-card {
            background: white;
            width: 100%;
            max-width: 450px;
            padding: 2rem;
            border-radius: 1.5rem;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        .header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .order-summary {
            background: #f9fafb;
            padding: 1.5rem;
            border-radius: 1rem;
            margin-bottom: 2rem;
        }

        .item-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-top: 1rem;
            padding-top: 1rem;
            border-top: 2px solid #e5e7eb;
            font-weight: 800;
            font-size: 1.25rem;
        }

        .payment-methods h3 {
            font-size: 1rem;
            margin-bottom: 1rem;
            color: #4b5563;
        }

        .method-btn {
            width: 100%;
            padding: 1rem;
            margin-bottom: 0.75rem;
            border: 2px solid #e5e7eb;
            border-radius: 0.75rem;
            background: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 600;
            transition: all 0.2s;
        }

        .method-btn:hover {
            border-color: var(--primary-color);
            background: #eff6ff;
        }

        .method-btn.active {
            border-color: var(--primary-color);
            background: #eff6ff;
        }

        .pay-now-btn {
            width: 100%;
            background: var(--primary-color);
            color: white;
            border: none;
            padding: 1.25rem;
            border-radius: 0.75rem;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            margin-top: 1rem;
            transition: opacity 0.2s;
        }

        .pay-now-btn:hover {
            opacity: 0.9;
        }

        .security-footer {
            margin-top: 1.5rem;
            text-align: center;
            font-size: 0.85rem;
            color: #6b7280;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }

        .badge {
            background: #dcfce7;
            color: #166534;
            padding: 4px 8px;
            border-radius: 6px;
            font-size: 0.75rem;
            font-weight: 600;
        }
    </style>
</head>
<body>

    <div class="checkout-card">
        <div class="header">
            <h2>Kassa</h2>
            <p>Slutför din beställning säkert</p>
        </div>

        <div class="order-summary">
            <div class="item-row">
                <span>Premium-tjänst</span>
                <span>149,00 kr</span>
            </div>
            <div class="item-row" style="color: #6b7280; font-size: 0.9rem;">
                <span>Moms (25%)</span>
                <span>37,25 kr</span>
            </div>
            <div class="total-row">
                <span>Totalt att betala</span>
                <span>149,00 kr</span>
            </div>
        </div>

        <div class="payment-methods">
            <h3>Välj betalsätt</h3>
            
            <button class="method-btn active">
                <span style="font-size: 1.5rem;">💳</span> 
                Betala med Kort
            </button>
            
            <button class="method-btn">
                <span style="font-size: 1.5rem;">📄</span> 
                Faktura (Klarna)
            </button>
        </div>

        <button class="pay-now-btn" onclick="processOrder()">
            Slutför köp
        </button>

        <div class="security-footer">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                <rect x="3" y="11" width="18" height="11" rx="2" ry="2"></rect>
                <path d="M7 11V7a5 5 0 0 1 10 0v4"></path>
            </svg>
            Säkrad med 256-bitars HTTPS-kryptering
        </div>
        
        <div style="text-align: center; margin-top: 10px;">
            <span class="badge">Ingen kortdata sparas på vår server</span>
        </div>
    </div>

    <script>
        function processOrder() {
            const btn = document.querySelector('.pay-now-btn');
            btn.disabled = true;
            btn.innerText = "Bearbetar...";
            
            // Simulerar en säker anslutning
            setTimeout(() => {
                alert("Beställningen mottagen! (Detta är en demo-sida)");
                btn.disabled = false;
                btn.innerText = "Slutför köp";
            }, 1500);
        }
    </script>

</body>
</html>
