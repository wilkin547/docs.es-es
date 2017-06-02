---
title: "C&#243;mo: Definir y usar proveedores de formato num&#233;rico personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "cadenas de formato personalizado"
  - "cadenas de formato numérico personalizado"
  - "mostrar datos de fecha y hora"
  - "proveedores de formato [.NET Framework]"
  - "dar formato [.NET Framework], números"
  - "dar formato a números [.NET Framework]"
  - "números [.NET Framework], cadenas de formato numérico personalizado"
  - "cadenas de formato numérico [.NET Framework]"
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Definir y usar proveedores de formato num&#233;rico personalizado
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona un amplio control sobre la representación de cadena de los valores numéricos.  Admite las características siguientes para personalizar el formato de los valores numéricos:  
  
-   Cadenas de formato numérico estándar, que proporcionan un conjunto predefinido de formatos para convertir los números en su representación de cadena.  Pueden utilizarse con cualquier método de formato numérico, como <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName>, que tiene un parámetro `format`.  Para obtener información detallada, vea [Cadenas con formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Cadenas de formato numérico personalizadas, que proporcionan un conjunto de símbolos que pueden combinarse para definir los especificadores de formato numérico personalizados.  También pueden utilizarse con cualquier método de formato numérico, como <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName>, que tiene un parámetro `format`.  Para obtener información detallada, vea [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Objetos <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo>, que definen los símbolos y los modelos de formato que se utilizan para mostrar las representaciones de cadena de los valores numéricos.  Pueden utilizarse con cualquier método de formato numérico, como <xref:System.Int32.ToString%2A>, que tiene un parámetro `provider`.  Normalmente, el parámetro `provider` se utiliza para determinar el formato específico de la referencia cultural.  
  
 En algunos casos \(como cuando una aplicación debe mostrar un número de cuenta, un número de identificación o un código postal con formato\) estas tres técnicas no resultan apropiadas.  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] también permite definir un objeto de formato que no es ni un objeto <xref:System.Globalization.CultureInfo> ni un objeto <xref:System.Globalization.NumberFormatInfo> para determinar el modo en que debe aplicarse formato a un valor numérico.  En este tema se proporcionan instrucciones paso a paso para implementar este tipo de objetos y se incluye un ejemplo en el que se da formato a números de teléfono.  
  
### Para definir un proveedor de formato personalizado  
  
1.  Defina una clase que implemente las interfaces <xref:System.IFormatProvider> e <xref:System.ICustomFormatter>.  
  
2.  Implemente el método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName>.  <xref:System.IFormatProvider.GetFormat%2A> es un método de devolución de llamada al que invoca el método de formato \(por ejemplo, el método [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\) para recuperar el objeto que es realmente responsable de realizar la operación de formato personalizado.  Una implementación típica de <xref:System.IFormatProvider.GetFormat%2A> hace lo siguiente:  
  
    1.  Determina si el objeto <xref:System.Type> pasado como parámetro del método representa una interfaz <xref:System.ICustomFormatter>.  
  
    2.  Si el parámetro representa la interfaz <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> devuelve un objeto que implementa la interfaz <xref:System.ICustomFormatter> que es responsable de proporcionar el formato personalizado.  Normalmente, el objeto de formato personalizado se devuelve a sí mismo.  
  
    3.  Si el parámetro no representa la interfaz <xref:System.ICustomFormatter>, <xref:System.IFormatProvider.GetFormat%2A> devuelve `null`.  
  
3.  Implemente el método <xref:System.ICustomFormatter.Format%2A>.  El método [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> invoca a este método, que es responsable de devolver la representación de cadena de un número.  Normalmente, la implementación del método conlleva las operaciones siguientes:  
  
    1.  De manera opcional, se examina el parámetro `provider` para asegurarse de que el método realmente se haya diseñado para proporcionar servicios de formato.  En el caso de los objetos de formato que implementan <xref:System.IFormatProvider> e <xref:System.ICustomFormatter>, esto implica probar la igualdad del parámetro `provider` con el objeto de formato actual.  
  
    2.  Se determina si el objeto de formato debe admitir especificadores de formato personalizados. \(Por ejemplo, una “n” especificador de formato podría indicarme que un número de teléfono de EE.UU. se debería representar en formato NANP, y “” podría indicar la salida en formato de la recomendación E.123 de ITU\-T\). Si se utilizan especificadores de formato, el método debe controlar el especificador de formato indicado.  Se pasa al método en el parámetro `format`.  Si no hay ningún especificador presente, el valor del parámetro `format` es <xref:System.String.Empty?displayProperty=fullName>.  
  
    3.  Se recupera el valor numérico que se pasó al método como parámetro `arg`.  Se llevan a cabo todas las manipulaciones necesarias para convertirlo en su representación de cadena.  
  
    4.  Se devuelve la representación de cadena del parámetro `arg`.  
  
### Para utilizar un objeto de formato numérico personalizado  
  
1.  Cree una nueva instancia de la clase de formato personalizado.  
  
2.  Llame al método de formato [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> pasándole el objeto de formato personalizado, el especificador de formato \(o <xref:System.String.Empty?displayProperty=fullName>, si no se va a usar ninguno\) y el valor numérico al que se va a dar formato.  
  
## Ejemplo  
 El ejemplo siguiente define un proveedor de formato numérico personalizado denominado `TelephoneFormatter` que convierte un número que representa un número de teléfono de EE.UU. en su formato NANP o E.123.  El método controla dos especificadores de formato, "N" \(que ofrece el resultado en formato NANP\) e "I" \(que ofrece el resultado en formato E.123 internacional\).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 El proveedor de formato numérico personalizado sólo puede utilizarse con el método [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  Todas las demás sobrecargas de los métodos de formato numérico \(como `ToString`\) que tienen un parámetro de tipo <xref:System.IFormatProvider> pasan a la implementación de <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName> un objeto <xref:System.Type> que representa el tipo <xref:System.Globalization.NumberFormatInfo>.  A cambio, esperan que el método devuelva un objeto <xref:System.Globalization.NumberFormatInfo>.  Si no lo hace, el proveedor de formato numérico personalizado se omite y, en su lugar, se utiliza el objeto <xref:System.Globalization.NumberFormatInfo> de la referencia cultural actual.  En el ejemplo, el método `TelephoneFormatter.GetFormat` controla la posibilidad de que se pueda haber pasado por error en un método de formato numérico; para ello, examina el parámetro y devuelve `null` si representa un tipo distinto de <xref:System.ICustomFormatter>.  
  
 Si un proveedor de formato numérico personalizado admite un conjunto de especificadores de formato, asegúrese de que proporcione un comportamiento predeterminado si no se proporciona ningún especificador de formato en el elemento de formato utilizado en la llamada al método [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  En el ejemplo, "N" es el especificador de formato predeterminado.  De este modo, un número puede convertirse en un número de teléfono con formato al proporcionar un especificador de formato explícito.  En el siguiente ejemplo se ilustra este tipo de llamada a un método.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Pero también permite que se realice la conversión si no hay ningún especificador de formato presente.  En el siguiente ejemplo se ilustra este tipo de llamada a un método.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Si no se define ningún especificador de formato predeterminado, la implementación del método <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName> debe incluir código como el siguiente para que .NET Framework pueda proporcionar el formato que su código no admite.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 En el caso de este ejemplo, se pretende que el método que implementa <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName> actúe como un método de devolución de llamada para el método [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>.  Por lo tanto, examina el parámetro `formatProvider` para determinar si contiene una referencia al objeto `TelephoneFormatter` actual.  Sin embargo, también se puede llamar al método directamente desde el código.  En ese caso, puede utilizar el parámetro `formatProvider` para proporcionar un objeto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> que proporcione información de formato específica de la referencia cultural.  
  
## Compilar el código  
 Compile el código de la línea de comandos mediante csc.exe o vb.exe.  Para compilar el código de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)