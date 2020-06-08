---
title: 'Procedimiento Determinar si una cadena representa un valor numérico: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 37437460ea4c6ca216f2844d63af3688ccc984c6
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241726"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a>Procedimiento Determinar si una cadena representa un valor numérico (Guía de programación de C#)
Para determinar si una cadena es una representación válida de un tipo numérico especificado, use el método estático `TryParse` implementado por todos los tipos numéricos primitivos y también por tipos como <xref:System.DateTime> y <xref:System.Net.IPAddress>. En el ejemplo siguiente se muestra cómo determinar si "108" es un valor [int](../../language-reference/builtin-types/integral-numeric-types.md) válido.  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Si la cadena contiene caracteres no numéricos o el valor numérico es demasiado grande o demasiado pequeño para el tipo determinado que ha especificado, `TryParse` devuelve el valor false y establece el parámetro out en cero. De lo contrario, devuelve el valor true y establece el parámetro out en el valor numérico de la cadena.  
  
> [!NOTE]
> Una cadena puede contener solamente caracteres numéricos pero no ser válida para el tipo cuyo método `TryParse` se está usando. Por ejemplo, "256" no es un valor válido para `byte` pero sí para `int`. "98,6" no es un valor válido para `int` pero sí para `decimal`.  
  
## <a name="example"></a>Ejemplo  
 En los ejemplos siguientes se muestra cómo usar `TryParse` con representaciones de cadena de los valores `long`, `byte` y `decimal`.  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Los tipos numéricos primitivos también implementan el método estático `Parse`, que produce una excepción si la cadena no es un número válido. `TryParse` es, en general, más eficaz porque simplemente devuelve false si el número no es válido.  
  
## <a name="net-security"></a>Seguridad de .NET  
 Use siempre los métodos `TryParse` o `Parse` para validar los datos proporcionados por el usuario en controles como cuadros de texto y cuadros combinados.  
  
## <a name="see-also"></a>Vea también

- [Procedimiento Convertir una matriz de bytes en un valor int](../types/how-to-convert-a-byte-array-to-an-int.md)
- [Procedimiento Convertir una cadena en un número](../types/how-to-convert-a-string-to-a-number.md)
- [Procedimiento Convertir cadenas hexadecimales en tipos numéricos](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [Análisis de cadenas numéricas](../../../standard/base-types/parsing-numeric.md)
- [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
