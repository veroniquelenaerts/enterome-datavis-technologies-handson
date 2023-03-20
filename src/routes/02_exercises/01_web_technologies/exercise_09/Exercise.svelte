<script>
    const radius = 3;
    function circumference_sphere(r) {
        const circ = 2*Math.PI*r
        return circ.toFixed(2);
    }
</script>

<p>
    The circumference of a circle with radius {radius}m is {circumference_sphere(radius)} m.
</p>