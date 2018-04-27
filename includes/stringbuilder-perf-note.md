El uso de la indexación basada en caracteres con la propiedad <xref:System.Text.StringBuilder.Chars%2A> puede ser muy lento en las condiciones siguientes:

- La instancia de <xref:System.Text.StringBuilder> es grande (por ejemplo, consta de varias decenas de miles de caracteres).
- <xref:System.Text.StringBuilder> es "pesado". Es decir, las llamadas repetidas a métodos como <xref:System.Text.StringBuilder.Append%2A?displayProperty=nameWithType> han ampliado automáticamente la propiedad <xref:System.Text.StringBuilder.Capacity%2A?displayProperty=nameWithType> del objeto y le han asignado nuevos fragmentos de memoria.

El rendimiento se ve seriamente afectado ya que cada acceso de carácter recorre toda la lista vinculada de fragmentos para buscar el búfer correcto en el que indexar.

> [!NOTE]
>  Incluso para un gran objeto <xref:System.Text.StringBuilder> pesado, el uso de la propiedad <xref:System.Text.StringBuilder.Chars%2A> para el acceso basado en índice a uno o un número reducido de caracteres tiene un efecto insignificante en el rendimiento; por lo general, es una operación **0(n)**. El impacto significativo en el rendimiento se produce al recorrer en iteración los caracteres del objeto <xref:System.Text.StringBuilder>, una operación **O(n^2)**. 

Si encuentra problemas de rendimiento al usar la indexación basada en caracteres con objetos <xref:System.Text.StringBuilder>, puede usar cualquiera de las soluciones alternativas siguientes:

- Convertir la instancia de <xref:System.Text.StringBuilder> en una <xref:System.String> mediante una llamada al método <xref:System.Text.StringBuilder.ToString%2A> y después obtener acceso a los caracteres de la cadena.

- Copiar el contenido del objeto <xref:System.Text.StringBuilder> existente en un objeto <xref:System.Text.StringBuilder> nuevo de tamaño predefinido. El rendimiento mejora porque el objeto <xref:System.Text.StringBuilder> nuevo no es pesado. Por ejemplo:

   ```csharp
   // sbOriginal is the existing StringBuilder object
   var sbNew = new StringBuilder(sbOriginal.ToString(), sbOriginal.Length);
   ```
   ```vb
   ' sbOriginal is the existing StringBuilder object
   Dim sbNew = New StringBuilder(sbOriginal.ToString(), sbOriginal.Length)
   ```
- Establezca la capacidad inicial del objeto <xref:System.Text.StringBuilder> en un valor que sea aproximadamente igual a su tamaño máximo esperado mediante una llamada al constructor <xref:System.Text.StringBuilder.%23ctor(System.Int32)>. Tenga en cuenta que esto asigna el bloque completo de memoria aunque <xref:System.Text.StringBuilder> rara vez alcanza su capacidad máxima.
