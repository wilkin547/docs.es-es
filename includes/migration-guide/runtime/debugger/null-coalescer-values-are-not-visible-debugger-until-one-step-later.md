### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior

|   |   |
|---|---|
|Detalles|Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.|
|Sugerencia|Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente. Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

