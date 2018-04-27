### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a>La revisión ortográfica de WPF en controles habilitados para texto no funcionará en Windows 10 para los idiomas no incluidos en la lista de idiomas de entrada del sistema operativo

|   |   |
|---|---|
|Detalles|Cuando se ejecuta en Windows 10, es posible que el corrector ortográfico no funcione para los controles habilitados para texto de WPF porque las funciones de revisión ortográfica de la plataforma solo están disponibles para los idiomas que aparecen en la lista de idiomas de entrada. En Windows 10, al agregar un idioma a la lista de teclados disponibles, Windows descarga e instala automáticamente un paquete de características previa petición (Feature on Demand, FOD) que proporciona funciones de revisión ortográfica. Al agregar el idioma a la lista de idiomas de entrada, se admitirá el corrector ortográfico.|
|Sugerencia|Tenga en cuenta que el idioma o el texto que se va a revisar se debe agregar como un idioma de entrada para que el corrector ortográfico funcione en Windows 10.|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

