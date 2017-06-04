---
title: "C&#243;mo: Convertir en n&#250;meros datos num&#233;ricos proporcionados por el usuario en controles web | Microsoft Docs"
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
  - "convertir entrada de datos numéricos del usuario en número"
  - "dar formato [.NET Framework], números"
  - "dar formato a números [.NET Framework]"
  - "números [.NET Framework], convertir entrada de datos numéricos del usuario en número"
  - "cadenas de formato numérico [.NET Framework]"
  - "analizar cadenas [.NET Framework], cadenas numéricas"
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Convertir en n&#250;meros datos num&#233;ricos proporcionados por el usuario en controles web
Dado que una página web se puede mostrar en cualquier parte del mundo, los usuarios pueden proporcionar datos numéricos en un control <xref:System.Web.UI.WebControls.TextBox> en un número casi ilimitado de formatos.  Por tanto, es muy importante determinar la configuración regional y la referencia cultural del usuario de la página web.  Cuando analice los datos proporcionados por el usuario, puede aplicar las convenciones de formato definidas por la configuración regional y la referencia cultural del usuario.  
  
### Para convertir la entrada numérica de un control web TextBox en un número  
  
1.  Determine si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> contiene elementos.  Si no es así, continúe en el paso 6.  
  
2.  Si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> contiene elementos, recupere el primer elemento.  El primer elemento indica el idioma y la región predeterminados o preferidos por el usuario.  
  
3.  Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural preferida del usuario; para ello, llame al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
4.  Llame al método `TryParse` o `Parse` del tipo numérico en el que desea convertir la entrada del usuario.  Utilice una sobrecarga del método `TryParse` o `Parse` con un parámetro `provider` y pásele cualquiera de los elementos siguientes:  
  
    -   El objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
    -   El objeto <xref:System.Globalization.NumberFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.NumberFormat%2A> del objeto <xref:System.Globalization.CultureInfo> que se creó en el paso 3.  
  
5.  Si la conversión no se realiza correctamente, repita los pasos 2 al 4 en cada elemento restante de la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6.  Si la conversión sigue produciendo errores o si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena usando la referencia cultural de todos los idiomas devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
## Ejemplo  
 El ejemplo siguiente corresponde a la página completa de código subyacente de un formulario web en la que se pide al usuario que escriba un valor numérico en un control <xref:System.Web.UI.WebControls.TextBox> y se convierte en un número.  Ese número se duplica y se muestra a continuación utilizando las mismas reglas de formato que la entrada original.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 La propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> se rellena a partir de los nombres de la referencia cultural incluidos en los encabezados `Accept-Language` de una solicitud HTTP.  Sin embargo, no todos los exploradores incluyen encabezados `Accept-Language` en sus solicitudes y además los usuarios pueden suprimir los encabezados por completo.  Por ello, es importante tener una referencia cultural de reserva al analizar los datos proporcionados por el usuario.  Por lo general, la referencia cultural de reserva es la referencia cultural de todos los idiomas devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Los usuarios también pueden proporcionar a Internet Explorer nombres de la referencia cultural escribiéndolos en un cuadro de texto, de modo que es posible que los nombres de la referencia cultural no sean válidos.  Por todo esto, es importante utilizar el control de excepciones al crear instancias de un objeto <xref:System.Globalization.CultureInfo>.  
  
 Cuando se recupera de una solicitud HTTP enviada por Internet Explorer, la matriz <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> se rellena en orden de preferencia del usuario.  El primer elemento de la matriz contiene el nombre de la referencia cultural o región primaria del usuario.  Si la matriz contiene algún otro elemento, Internet Explorer le asigna arbitrariamente un especificador de calidad, que está delimitado del nombre de la referencia cultural mediante un punto y coma.  Por ejemplo, una entrada para la referencia cultural fr\-FR podría tener la forma `fr-FR;q=0.7`.  
  
 En el ejemplo, se llama al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A> con el parámetro `useUserOverride` establecido en `false` para crear un nuevo objeto <xref:System.Globalization.CultureInfo>.  De este modo, tiene la seguridad de que si el nombre de la referencia cultural es el nombre de la referencia cultural predeterminada del servidor, el nuevo objeto <xref:System.Globalization.CultureInfo> creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas con la aplicación **Configuración regional y de idioma** del servidor.  Es poco probable que los valores de una configuración invalidada en el servidor permanezcan en el sistema del usuario o se reflejen en los datos proporcionados por el usuario.  
  
 Su código puede llamar al método `Parse` o `TryParse` del tipo numérico en el que se convertirá la entrada del usuario.  Puede ser necesario llamar varias veces a un método de análisis en una única operación de análisis.  Como resultado, el método `TryParse` resulta más conveniente porque devuelve `false` si se producen errores en una operación de análisis.  Por el contrario, mantener un control sobre las excepciones repetidas que puede producir el método `Parse` puede ser una tarea excesivamente costosa cuando se trata de una aplicación web.  
  
## Compilar el código  
 Para compilar el código, cópielo en una página de código subyacente de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] para que reemplace todo el código existente.  La página web de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] debe contener los controles siguientes:  
  
-   Un control <xref:System.Web.UI.WebControls.Label>, al que no se hace referencia en código.  Establezca la propiedad <xref:System.Web.UI.WebControls.TextBox.Text%2A> en "Escriba un número:".  
  
-   Un control <xref:System.Web.UI.WebControls.TextBox> denominado `NumericString`.  
  
-   Un control <xref:System.Web.UI.WebControls.Button> denominado `OKButton`.  Establezca la propiedad <xref:System.Web.UI.WebControls.Button.Text%2A> en "Aceptar".  
  
 Cambie el nombre de la clase de `NumericUserInput` por el nombre de la clase definido por el atributo `Inherits` de la directiva `Page` de la página de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  Cambie el nombre de la referencia del objeto `NumericInput` por al nombre definido en el atributo `id` de la etiqueta `form` de la página de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
## Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en la secuencia HTML, los datos proporcionados por el usuario nunca deberían devolverse directamente en la respuesta del servidor.  En su lugar, deberían codificarse con el método <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName>.  
  
## Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Analizar cadenas numéricas](../../../docs/standard/base-types/parsing-numeric.md)