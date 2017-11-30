---
title: "Cómo: Convertir en números datos numéricos proporcionados por el usuario en controles web"
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
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Cómo: Convertir en números datos numéricos proporcionados por el usuario en controles web
Dado que una página Web puede mostrarse en cualquier lugar del mundo, los usuarios pueden proporcionar datos numéricos en un <xref:System.Web.UI.WebControls.TextBox> control en un número casi ilimitado de formatos. Como resultado, es muy importante determinar la configuración regional y la referencia cultural del usuario de la página Web. Cuando se analiza proporcionados por el usuario, a continuación, puede aplicar las convenciones de formato definidas por la configuración regional y la referencia cultural del usuario.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Para convertir la entrada numérica de un control de cuadro de texto Web en un número  
  
1.  Determinar si la matriz de cadena devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad se rellena. Si no es así, vaya al paso 6.  
  
2.  Si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad se rellena, recupere el primer elemento. El primer elemento indica el usuario predeterminado o idioma preferido y región.  
  
3.  Crear una instancia de un <xref:System.Globalization.CultureInfo> objeto que representa al usuario preferido referencia cultural mediante una llamada a la <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> constructor.  
  
4.  Llamar a la `TryParse` o `Parse` de tipo numérico que se va a convertir el usuario de entrada del método a. Use una sobrecarga de la `TryParse` o `Parse` método con un `provider` parámetro y pasar cualquiera de las siguientes acciones:  
  
    -   La <xref:System.Globalization.CultureInfo> objeto creado en el paso 3.  
  
    -   El <xref:System.Globalization.NumberFormatInfo> objeto devuelto por la <xref:System.Globalization.CultureInfo.NumberFormat%2A> propiedad de la <xref:System.Globalization.CultureInfo> objeto creado en el paso 3.  
  
5.  Si se produce un error en la conversión, repita los pasos del 2 al 4 para cada elemento restante en la matriz de cadenas devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad.  
  
6.  Si todavía se produce un error en la conversión o si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad está vacía, analizar la cadena usando la referencia cultural, lo que es devuelto por la <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente es la página completa de código subyacente de un formulario Web Forms que pide al usuario que escriba un valor numérico en un <xref:System.Web.UI.WebControls.TextBox> controlar y lo convierte en un número. A continuación, ese número es duplicado y se muestran utilizando las mismas reglas de formato como la entrada original.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 El <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad se rellena a partir de los nombres de referencia cultural que se encuentran en `Accept-Language` encabezados incluidos en una solicitud HTTP. Sin embargo, no todos los exploradores incluyen `Accept-Language` encabezados en sus solicitudes y los usuarios también pueden suprimir los encabezados por completo. Esto hace que sea importante tener una referencia cultural de reserva al analizar proporcionados por el usuario. Normalmente, la referencia cultural de reserva es la referencia cultural invariable devuelta por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Los usuarios también pueden proporcionar Internet Explorer con nombres de referencia cultural escribiéndolos en un cuadro de texto, que crea la posibilidad de que los nombres de referencia cultural pueden no ser válidos. Esto hace que sea importante para usar el control de excepciones al crear instancias de un <xref:System.Globalization.CultureInfo> objeto.  
  
 Cuando se recuperan de una solicitud HTTP enviada por Internet Explorer, la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> matriz se rellena en orden de preferencia de usuario. El primer elemento de la matriz contiene el nombre de referencia cultural/región principal del usuario. Si la matriz contiene los elementos adicionales, Internet Explorer le asigna arbitrariamente un especificador de calidad, que está delimitado del nombre de referencia cultural de un punto y coma. Por ejemplo, una entrada para la referencia cultural fr-FR podría tener el formato `fr-FR;q=0.7`.  
  
 El ejemplo se llama el <xref:System.Globalization.CultureInfo.%23ctor%2A> constructor con su `useUserOverride` parámetro establecido en `false` para crear un nuevo <xref:System.Globalization.CultureInfo> objeto. Esto garantiza que, si el nombre de referencia cultural es el nombre de la referencia cultural predeterminada en el servidor, el nuevo <xref:System.Globalization.CultureInfo> objeto creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas con el servidor  **Regional y de idioma** aplicación. Los valores de una configuración invalidada en el servidor son poco probable que exista en el sistema del usuario o para que se refleje en la entrada del usuario.  
  
 El código puede llamar a la `Parse` o `TryParse` método de tipo numérico que la entrada del usuario se convertirá en. Las llamadas repetidas a un método de análisis pueden resultar necesarias para una única operación de análisis. Como resultado, el `TryParse` métodos es mejor, porque devuelve `false` si se produce un error en una operación de análisis. En cambio, controlar las excepciones repetidas que pueden producir el `Parse` método puede ser una propuesta muy costosa en una aplicación Web.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el código, cópielo en un [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] página de código subyacente, por lo que reemplaza todo el código existente. La [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] página Web debe contener los siguientes controles:  
  
-   Un <xref:System.Web.UI.WebControls.Label> control, que no se hace referencia en el código. Establecer su <xref:System.Web.UI.WebControls.TextBox.Text%2A> propiedad en "Escriba un número:".  
  
-   Un control <xref:System.Web.UI.WebControls.TextBox> llamado `NumericString`.  
  
-   Un control <xref:System.Web.UI.WebControls.Button> llamado `OKButton`. Establecer su <xref:System.Web.UI.WebControls.Button.Text%2A> propiedad en "Aceptar".  
  
 Cambiar el nombre de la clase de `NumericUserInput` en el nombre de la clase definida por el `Inherits` atributo de la [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] la página `Page` directiva. Cambiar el nombre de la `NumericInput` objetos hacen referencia al nombre definido por el `id` atributo de la [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] la página `form` etiqueta.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en el flujo HTML, los proporcionados por el usuario nunca deben devolverse directamente en la respuesta del servidor. En su lugar, debe codificarse utilizando el <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> método.  
  
## <a name="see-also"></a>Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Análisis de cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)
