<script>
  let allPorts = '';

  const serialport = require('serialport');
  const tableify = require('tableify');
  const j$ = require('jquery');

  serialport.list((err, ports) => {
    console.log('ports', ports);
    if (err) {
      console.log('No ports was found');
      return;
    }
    console.log('No ports was found');

    if (ports.length === 0) {
      console.log('No ports was found');
    }
    console.log(ports);
    allPorts = tableify(ports);
    j$('.mytable').html(allPorts);
  });
</script>

<div class="mytable" />
