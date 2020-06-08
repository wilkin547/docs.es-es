---
title: Procedimiento para definir y usar proveedores de formato numérico personalizado
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
ms.openlocfilehash: d12899fff7d9e6cb63728ba0b160b70fa2a41a1a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290518"
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Procedimiento para definir y usar proveedores de formato numérico personalizado
.NET Framework ofrece un amplio control sobre la representación de cadena de valores numéricos. Admite las siguientes características para personalizar el formato de los valores numéricos:  
  
- Cadenas con formato numérico estándar, que proporcionan un conjunto predefinido de formatos para convertir números en su representación de cadena. Se pueden usar con cualquier método de formato numérico, como <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, que tiene un parámetro `format`. Para obtener detalles, vea [Cadenas con formato numérico estándar](standard-numeric-format-strings.md).  
  
- Cadenas con formato numérico personalizado, que proporcionan un conjunto de símbolos que pueden combinarse para definir especificadores de formato numérico personalizado. Se pueden usar también con cualquier método de formato numérico, como <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, que tiene un parámetro `format`. Para obtener detalles, consulte [Cadenas con formato numérico personalizado](custom-numeric-format-strings.md).  
  
- Objetos personalizados <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo>, que definen los símbolos y los modelos de formato que se usan para mostrar las representaciones de cadena de valores numéricos. Se pueden usar con cualquier método de formato numérico, como <xref:System.Int32.ToString%2A>, que tiene un parámetro `provider`. Normalmente, el parámetro `provider` se usa para especificar el formato específico de la referencia cultural.  
  
 En algunos casos (por ejemplo, cuando una aplicación debe mostrar un número de cuenta con formato, un número de identificación o un código postal) estas tres técnicas no resultan apropiadas. .NET Framework también permite definir un objeto de formato que no es ni un objeto <xref:System.Globalization.CultureInfo> ni <xref:System.Globalization.NumberFormatInfo> para determinar cómo se aplica formato a un valor numérico. En este tema se proporcionan instrucciones paso a paso para implementar este tipo de objeto y se ofrece un ejemplo que da formato a números de teléfono.  
  
### <a name="to-define-a-custom-format-provider"></a>Para definir un proveedor de formato personalizado  
  
1. Defina una clase que implementa las interfaces <xref:System.IFormatProvider> y <xref:System.ICustomFormatter>.  
  
2. Implemente el método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A> es un método de devolución de llamada que el método de formato (como el método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>) invoca para recuperar el objeto realmente responsable del formato personalizado. Una implementación típica de <xref:System.IFormatProvider.GetFormat%2A> hace lo siguiente:  
  
    1. Determina si el objeto <xref:System.Type> pasado como un parámetro de método representa a una interfaz <xref:System.ICustomFormatter>.  
  
    2. Si el parámetro representa a la interfaz <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> devuelve un objeto que implementa la interfaz <xref:System.ICustomFormatter>, que es responsable de proporcionar el formato personalizado. Normalmente, el objeto de formato personalizado se devuelve a sí mismo.  
  
    3. Si el parámetro no representa la interfaz <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> devuelve `null`.  
  
3. Implemente el método <xref:System.ICustomFormatter.Format%2A>. Este método es invocado por el método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> y es responsable de devolver la representación de cadena de un número. La implementación del método normalmente implica lo siguiente:  
  
    1. Opcionalmente, asegúrese de que el método se haya diseñado para proporcionar servicios de formato al examinar el parámetro `provider`. En el caso de los objetos de formato que implementan <xref:System.IFormatProvider> y <xref:System.ICustomFormatter>, esto implica probar la igualdad del parámetro `provider` y el objeto de formato actual.  
  
    2. Determine si el objeto de formato debe admitir especificadores de formato personalizado. (Por ejemplo, un especificador de formato "N" podría indicar que debe generarse un número de teléfono de los Estados Unidos en formato NANP, mientras que una "I" podría indicar la salida en el formato de la recomendación E.123 de ITU-T). Si se usan especificadores de formato, el método debe controlar el especificador de formato específico. Se pasa al método en el parámetro `format`. Si no hay ningún especificador, el valor del parámetro `format` es <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3. Recupere el valor numérico pasado al método como parámetro `arg`. Realice todas las manipulaciones necesarias para convertirlo en su representación de cadena.  
  
    4. Devuelva la representación de cadena del parámetro `arg`.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Para usar un objeto de formato numérico personalizado  
  
1. Cree una nueva instancia de la clase de formato personalizado.  
  
2. Llame al método de formato <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> y pásele el objeto de formato personalizado, el especificador de formato (o <xref:System.String.Empty?displayProperty=nameWithType> si no se usa ninguno) y el valor numérico al que se va a dar formato.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un proveedor de formato numérico personalizado denominado `TelephoneFormatter` que convierte un número que representa un número de teléfono de los Estados Unidos en su formato NANP o E.123. El método controla dos especificadores de formato, "N" (que genera el formato NANP) e "I" (que genera el formato E.123 internacional).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 El proveedor de formato numérico personalizado puede utilizarse solo con el método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Las demás sobrecargas de métodos de formato numérico (como `ToString`) que tienen un parámetro de tipo <xref:System.IFormatProvider> pasan a la implementación de <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> un objeto <xref:System.Type> que representa al tipo <xref:System.Globalization.NumberFormatInfo>. A cambio, esperan que el método devuelva un objeto <xref:System.Globalization.NumberFormatInfo>. Si no es así, se omite el proveedor de formato numérico personalizado y se usa el objeto <xref:System.Globalization.NumberFormatInfo> de la referencia cultural actual en su lugar. En el ejemplo, el método `TelephoneFormatter.GetFormat` controla la posibilidad de que se pueda pasar incorrectamente a un método de formato numérico al examinar el parámetro de método y devolver `null` si representa a un tipo distinto de <xref:System.ICustomFormatter>.  
  
 Si un proveedor de formato numérico personalizado admite un conjunto de especificadores de formato, asegúrese de proporcionar un comportamiento predeterminado si no se proporciona ningún especificador de formato en el elemento de formato usado en la llamada al método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. En el ejemplo, "N" es el especificador de formato predeterminado. Esto permite convertir un número en un número de teléfono con formato al proporcionar un especificador de formato explícito. En el ejemplo siguiente se muestra una llamada al método así.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Pero también permite que se produzca la conversión si no hay ningún especificador de formato. En el ejemplo siguiente se muestra una llamada al método así.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Si no se ha definido ningún especificador de formato predeterminado, la implementación del método <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> debe incluir código como el siguiente para que .NET pueda proporcionar formato no admitido por el código.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 En el caso de este ejemplo, el método que implementa <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> está diseñado para que actúe como un método de devolución de llamada para el método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>. Por lo tanto, examina el parámetro `formatProvider` para determinar si contiene una referencia al objeto `TelephoneFormatter` actual. Pero también se puede llamar al método directamente desde el código. En ese caso, puede usar el parámetro `formatProvider` para proporcionar un objeto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> que aporte información de formato específica de la referencia cultural.
