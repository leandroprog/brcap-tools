# brcap-tools
Biblioteca de ferramentas criadas para facilitar o desenvolvimento

## Instalação
`$ npm install brcap-tools`

## Método utilitário para criação de PDF
Exemplo de utilização:
```javascript
  const { exportTo } = require('brcap-tools');

  const data = [
  { // todas as propriedades são opcionais
    style: {}, //  (wrapper style) javascript style, expl: backgroundColor e não background-color
    logo: {
      // src: "http://....."
      src: 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQAAAABKBAMAAACm6JfrAAAAG1BMVEXMzMyWlpbFxcWcnJy+vr63t7ejo6OxsbGqqqoXdgqcAAABkklEQVRo3u3UMY6bQBSA4d8YbJf7PAa7xFibbc1GclrICSAnMJsLwErpIbl43pBdW5HSpJhipfcVjDQNv55mBmOMMcYYY4wxxvyPdfcFjiJSEf3KKu5iUQfgdCagSeRKPQecRNJ/BUwhA2JXnVLar0UB089Ycu6Kovi08yEhAzY74owhR2UwNPylHmHZhQxYPoBjQiUpPOa6Oph6Zp/RqDpowBlKvpPDZqtfr+tjB+9N0WERMiDKiRyXwfWstpNrUPV2ld7ydFsDgtrsEZGM5UXk8GejvjJre81pQgdMz5G8PkqzkG9PUvmpSFkxK4ELgQNOLo9+QHtdpDCMqOHALNZ1vQsckMgLSv/iL8TxiqrT2x3l+FIcn3PCaffv93F11ow5oHP3O1qLeiCYqGwgefUT2PgJjH7yWdfg1WP4gLUfQKKfdozTt5dwuXt7eoYeFfYMrLbzsW8SySmbJ4dqr6s9XleFD1iKYhDxQxDZocoq0hwlhA9YiCLpsgbiLsuBdQbT6AfjbgHGGGOMMcYYYz6Y31FHNHBDS2AwAAAAAElFTkSuQmCC',
      alt: 'logo', // atributo obrigatório
      style: {},
    },
    title: { innerHTML: 'FIRST PAGE', style: {} }, // innerHTML aceita tbm html, expl: innerHTML: '<span class="red" style="color: 'red';">Lorem Ipsum</spam>'
    descLeft: { innerHTML: 'Description left', style: {} },
    descRight: { innerHTML: 'Description right', style: {} },
    counter: { innerHTML: 'page $1/$2', style: {} }, // $1 = pagina atual, $2 = paginas total
    table: {
      style: {},
      thead: [
        [{ innerHTML: 'dados titulo', style: {} }, { innerHTML: 'dados titulo', style: {} }],
      ],
      tbody: [
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
        [{ innerHTML: 'dados', style: {} }, { innerHTML: 'dados', style: {} }],
      ],
    },
  },
  { // Próxima página
    title: { innerHTML: 'SECOND PAGE', style: {} },
  },
];
// download inicia automaticamente
// Retorna false se browser não for chrome
const result = exportTo.pdf.table(data, 'filename');
// Formato portrait e ignora a verificação de chrome
const result = exportTo.pdf.table(data, 'filename', 'p', true);
```