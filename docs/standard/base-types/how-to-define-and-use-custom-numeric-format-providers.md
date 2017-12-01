---
title: "Cómo: Definir y usar proveedores de formato numérico personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Cómo: Definir y usar proveedores de formato numérico personalizado
El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] ofrece un amplio control sobre la representación de cadena de valores numéricos. Admite las siguientes características para personalizar el formato de los valores numéricos:  
  
-   Cadenas con formato numérico estándar, que proporcionan un conjunto predefinido de formatos para convertir números en su representación de cadena. También puede utilizarlos con cualquier método de formato como numérico <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, que tiene un `format` parámetro. Para obtener más información, consulte [cadenas de formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Cadenas con formato numérico personalizado, que proporcionan un conjunto de símbolos que pueden combinarse para definir especificadores de formato numérico personalizado. También pueden usarse con cualquier método de formato como numérico <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, que tiene un `format` parámetro. Para obtener más información, consulte [cadenas de formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Personalizado <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> objetos, que definen los símbolos y patrones que se utilizan para mostrar las representaciones de cadena de valores numéricos de formato. También puede utilizarlos con cualquier método de formato como numérico <xref:System.Int32.ToString%2A>, que tiene un `provider` parámetro. Normalmente, el `provider` parámetro se utiliza para especificar el formato específico de la referencia cultural.  
  
 En algunos casos (por ejemplo, cuando una aplicación debe mostrar un número de cuenta con formato, un número de identificación o un código postal) estas tres técnicas no resultan apropiadas. El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] también le permite definir un objeto de formato que no es ni un <xref:System.Globalization.CultureInfo> ni un <xref:System.Globalization.NumberFormatInfo> para determinar cómo se da formato a un valor numérico. En este tema se proporcionan instrucciones paso a paso para implementar este tipo de objeto y se ofrece un ejemplo que da formato a números de teléfono.  
  
### <a name="to-define-a-custom-format-provider"></a>Para definir un proveedor de formato personalizado  
  
1.  Defina una clase que implementa el <xref:System.IFormatProvider> y <xref:System.ICustomFormatter> interfaces.  
  
2.  Implemente el método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. <xref:System.IFormatProvider.GetFormat%2A>es un método de devolución de llamada que el método de formato (como el <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> método), se invoca para recuperar el objeto que es realmente responsable de la realización de formato personalizado. Una implementación típica de <xref:System.IFormatProvider.GetFormat%2A> hace lo siguiente:  
  
    1.  Determina si el <xref:System.Type> objeto pasado como un método parámetro representa un <xref:System.ICustomFormatter> interfaz.  
  
    2.  Si el parámetro representa el <xref:System.ICustomFormatter> interfaz, <xref:System.IFormatProvider.GetFormat%2A> devuelve un objeto que implementa el <xref:System.ICustomFormatter> interfaz que es responsable de proporcionar formatos personalizados. Normalmente, el objeto de formato personalizado se devuelve a sí mismo.  
  
    3.  Si el parámetro no representa la <xref:System.ICustomFormatter> interfaz, <xref:System.IFormatProvider.GetFormat%2A> devuelve `null`.  
  
3.  Implemente el método <xref:System.ICustomFormatter.Format%2A>. Este método es invocado por el <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> método y es responsable de devolver la representación de cadena de un número. La implementación del método normalmente implica lo siguiente:  
  
    1.  Si lo desea, asegúrese de que el método legítimamente está diseñado para proporcionar servicios de formato examinando el `provider` parámetro. Para dar formato a los objetos que implementan ambos <xref:System.IFormatProvider> y <xref:System.ICustomFormatter>, esto implica probar el `provider` parámetro igualdad con el objeto de formato actual.  
  
    2.  Determine si el objeto de formato debe admitir especificadores de formato personalizado. (Por ejemplo, un especificador de formato "N" podría indicar que debe generarse un número de teléfono de los Estados Unidos en formato NANP, mientras que una "I" podría indicar la salida en el formato de la recomendación E.123 de ITU-T). Si se usan especificadores de formato, el método debe controlar el especificador de formato específico. Se pasa al método en el `format` parámetro. Si no hay ningún especificador presente, el valor de la `format` parámetro es <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3.  Recuperar el valor numérico que se pasa al método como el `arg` parámetro. Realice todas las manipulaciones necesarias para convertirlo en su representación de cadena.  
  
    4.  Devolver la representación de cadena de la `arg` parámetro.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Para usar un objeto de formato numérico personalizado  
  
1.  Cree una nueva instancia de la clase de formato personalizado.  
  
2.  Llame a la <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> método de formato, pasándole el objeto de formato personalizado, el especificador de formato (o <xref:System.String.Empty?displayProperty=nameWithType>, si no se utiliza alguno) y el valor numérico para dar formato.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un proveedor de formato numérico personalizado denominado `TelephoneFormatter` que convierte un número que representa un número de teléfono de los Estados Unidos en su formato NANP o E.123. El método controla dos especificadores de formato, "N" (que genera el formato NANP) e "I" (que genera el formato E.123 internacional).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 El proveedor de formato numérico personalizado puede utilizarse solo con el <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> método. Las demás sobrecargas de métodos de formato numérico (como `ToString`) que tienen un parámetro de tipo <xref:System.IFormatProvider> superan todas las <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> implementación un <xref:System.Type> objeto que representa el <xref:System.Globalization.NumberFormatInfo> tipo. En cambio, esperan que el método devuelva un <xref:System.Globalization.NumberFormatInfo> objeto. Si no es así, se omite el proveedor de formato numérico personalizado y el <xref:System.Globalization.NumberFormatInfo> de objeto para la referencia cultural actual se utiliza en su lugar. En el ejemplo, el `TelephoneFormatter.GetFormat` método controla la posibilidad de que se puede pasar incorrectamente a un método de formato examinando el parámetro de método y devolver valor numérico `null` si representa un tipo distinto de <xref:System.ICustomFormatter>.  
  
 Si un proveedor de formato numérico personalizado admite un conjunto de especificadores de formato, asegúrese de proporcionar un comportamiento predeterminado si no se proporciona ningún especificador de formato en el elemento de formato usado en el <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> llamada al método. En el ejemplo, "N" es el especificador de formato predeterminado. Esto permite convertir un número en un número de teléfono con formato al proporcionar un especificador de formato explícito. En el ejemplo siguiente se muestra una llamada al método así.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Pero también permite que se produzca la conversión si no hay ningún especificador de formato. En el ejemplo siguiente se muestra una llamada al método así.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Si no se ha definido ningún especificador de formato de manera predeterminada, la implementación de la <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> método debe incluir código como el siguiente para que .NET puede proporcionar el formato que no es compatible con el código.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 En el caso de este ejemplo, el método que implementa <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> está diseñado para que actúe como un método de devolución de llamada para el <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> método. Por lo tanto, examina la `formatProvider` parámetro para determinar si contiene una referencia al actual `TelephoneFormatter` objeto. Pero también se puede llamar al método directamente desde el código. En ese caso, puede usar el `formatProvider` parámetro para proporcionar un <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> objeto que proporciona información de formato específica de la referencia cultural.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Compile el código de la línea de comandos mediante csc.exe o vb.exe. Para compilar el código de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], póngalo en una plantilla de proyecto de aplicación de consola.  
  
## <a name="see-also"></a>Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)
