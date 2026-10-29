        `Address: ${address}\n\n` +
        `${orderDetails}\n\n` +
        `Total: Rs. ${total}`;

    const whatsappNumber = "919699955142";

    window.open(
        "https://wa.me/" + whatsappNumber +
        "?text=" + encodeURIComponent(message),
        "_blank"
    );
}

displayProducts();
displayCart();
</script>

</body>
</html>