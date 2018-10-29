---
title: 'Cómo: Convertir en números datos numéricos proporcionados por el usuario en controles web'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 663f9d88315f396b187cca874c930179f1dea523
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49349142"
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Cómo: Convertir en números datos numéricos proporcionados por el usuario en controles web
Dado que una página web puede mostrarse en cualquier lugar del mundo, los usuarios pueden proporcionar datos numéricos en un control <xref:System.Web.UI.WebControls.TextBox> en un número casi ilimitado de formatos. Como resultado, es muy importante determinar la configuración regional y la referencia cultural del usuario de la página web. Al analizar las entradas del usuario, puede aplicar las convenciones de formato definidas por la configuración regional y la referencia cultural del usuario.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Para convertir la entrada numérica de un control de cuadro de texto web en un número  
  
1.  Determine si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena. Si no es así, vaya al paso 6.  
  
2.  Si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> se rellena, recupere el primer elemento. El primer elemento indica la región y el idioma preferidos o predeterminados del usuario.  
  
3.  Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural preferida del usuario con una llamada al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4.  Llame al método `TryParse` o `Parse` del tipo numérico en que desea convertir la entrada del usuario. Use una sobrecarga del método `TryParse` o `Parse` con un parámetro `provider` y pásela con lo siguiente:  
  
    -   El objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
    -   El objeto <xref:System.Globalization.NumberFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.NumberFormat%2A> del objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
5.  Si se produce un error en la conversión, repita los pasos 2 a 4 para cada elemento restante de la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6.  Si todavía existen errores de conversión o si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena con la referencia cultural invariable devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es la página de código subyacente completa de un formulario web que solicita al usuario que escriba un valor numérico en un control <xref:System.Web.UI.WebControls.TextBox> y lo convierte en un número. Ese número se duplica y se muestra con el uso de las mismas reglas de formato que la entrada original.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 La propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena a partir de los nombres de referencia cultural contenidos en los encabezados `Accept-Language` incluidos en una solicitud HTTP. Sin embargo, no todos los exploradores incluyen encabezados `Accept-Language` en sus solicitudes, y los usuarios también pueden suprimir los encabezados por completo. Esto hace que sea importante tener una referencia cultural de reserva al analizar la entrada del usuario. Normalmente, la referencia cultural de reserva es la referencia cultural invariable devuelta por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Los usuarios también pueden proporcionar a Internet Explorer nombres de referencia cultural que se escriben en un cuadro de texto, lo que plantea la posibilidad de que los nombres de referencia cultural no sean válidos. Esto hace que sea importante usar el control de excepciones al crear instancias de un objeto <xref:System.Globalization.CultureInfo>.  
  
 Cuando se recupera a partir de una solicitud HTTP enviada por Internet Explorer, la matriz <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena en función de las preferencias del usuario. El primer elemento de la matriz contiene el nombre de la región o referencia cultural principales del usuario. Si la matriz contiene elementos adicionales, Internet Explorer les asigna arbitrariamente un especificador de calidad, que está delimitado por un punto y coma desde el nombre de la referencia cultural. Por ejemplo, una entrada para la referencia cultural fr-FR podría tener el formato `fr-FR;q=0.7`.  
  
 El ejemplo llama al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A> con su parámetro `useUserOverride` establecido en `false` para crear un objeto <xref:System.Globalization.CultureInfo>. Esto garantiza que, si el nombre de la referencia cultural es el nombre de la referencia cultural predeterminado en el servidor, el nuevo objeto <xref:System.Globalization.CultureInfo> creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas al usar la aplicación **Configuración regional y de idioma** del servidor. Es poco probable que la configuración invalidada del servidor exista en el sistema del usuario o que se refleje en la entrada del usuario.  
  
 El código puede llamar al método `Parse` o `TryParse` del tipo numérico al que se convertirá la entrada del usuario. Puede que se necesiten llamadas repetidas a un método de análisis para una única operación de análisis. Como resultado, el método `TryParse` es mejor, porque devuelve `false` si se produce algún error con la operación de análisis. En cambio, controlar las excepciones repetidas que el método `Parse` puede ocasionar puede ser una propuesta muy costosa en una aplicación web.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el código, cópielo en una página de código subyacente [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], para que reemplace todo el código existente. La página web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] debe contener los siguientes controles:  
  
-   Un control <xref:System.Web.UI.WebControls.Label>, al que no se hace referencia en el código. Establezca su propiedad <xref:System.Web.UI.WebControls.TextBox.Text%2A> en "Enter a Number:".  
  
-   Control <xref:System.Web.UI.WebControls.TextBox> denominado `NumericString`.  
  
-   Control <xref:System.Web.UI.WebControls.Button> denominado `OKButton`. Establezca la propiedad <xref:System.Web.UI.WebControls.Button.Text%2A> en "OK".  
  
 Cambie el nombre de la clase `NumericUserInput` por el nombre de la clase definido por el atributo `Inherits` de la directiva `Page` de la página [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Cambie el nombre de la referencia de objeto `NumericInput` por el nombre definido por el atributo `id` de la etiqueta `form` de la página [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en la secuencia HTML, la entrada del usuario nunca debe devolverse directamente en la respuesta del servidor. En su lugar, debe codificarse con el método <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)  
- [Análisis de cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)
