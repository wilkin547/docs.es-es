---
title: "Atributos y comentarios sobre localizaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "localización, atributos"
  - "localización, comentarios"
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Atributos y comentarios sobre localizaci&#243;n
Los comentarios de localización de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] son propiedades, dentro del código fuente de [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], suministradas por los desarrolladores para proporcionar reglas y sugerencias para la localización.  Los comentarios de localización de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contienen dos conjuntos de información: los atributos de localización y los comentarios sobre localización de forma libre.  La API de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza los atributos de localización para indicar qué recursos se deben localizar.  Los comentarios de forma libre son cualquier información que el autor de la aplicación desea incluir.  
  
   
  
<a name="Localizer_Comments_"></a>   
## Comentarios de localización  
 Si los autores de una aplicación de marcado tienen requisitos para elementos concretos de [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], tales como restricciones en la longitud del texto, familia de fuentes o tamaño de fuente, pueden transmitir esta información a los localizadores mediante comentarios en el código [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  El proceso para agregar comentarios al código fuente es el siguiente:  
  
1.  El programador de la aplicación agrega los comentarios de localización al código fuente [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
2.  Durante el proceso de compilación, puede especificar en el archivo .proj si conservar los comentarios de localización de forma libre en el ensamblado, quitar parte de ellos o quitarlos todos.  Los comentarios quitados se colocan en un archivo independiente.  La opción se especifica mediante una etiqueta `LocalizationDirectivesToLocFile`, por ejemplo:  
  
     `<LocalizationDirectivesToLocFile>` *valor* `</LocalizationDirectivesToLocFile>`  
  
3.  Los valores que se pueden asignar son:  
  
    -   **None**: se conservan tanto los comentarios como los atributos en el ensamblado y no se genera ningún archivo independiente.  
  
    -   **CommentsOnly**: únicamente se quitan los comentarios del ensamblado y se colocan en el archivo LocFile independiente.  
  
    -   **All**: se quitan los comentarios y los atributos del ensamblado y se colocan en el archivo LocFile independiente.  
  
4.  Cuando los recursos localizables se extraen del [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)], la API de localización de [!INCLUDE[TLA2#tla_baml](../../../../includes/tla2sharptla-baml-md.md)] respeta los atributos de localización.  
  
5.  Los archivos de comentarios de localización, que únicamente contienen comentarios de forma libre, se incorporan al proceso de localización en un momento posterior.  
  
 En el ejemplo siguiente se muestra cómo agregar comentarios de localización a un archivo [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 En el ejemplo anterior, la sección Localization.Attributes contiene los atributos de localización, y la sección Localization.Comments, los comentarios de forma libre.  En las tablas siguientes se muestran los atributos y comentarios, así como su significado para el localizador.  
  
|Atributos de localización|Significado|  
|-------------------------------|-----------------|  
|$Content \(Unmodifiable Readable Text\)|No se puede modificar el contenido del elemento TextBlock.  Los localizadores no pueden cambiar la palabra "Microsoft".  El contenido está visible \(Readable\) para el localizador.  La categoría del contenido es Text \(texto\).|  
|FontFamily \(Unmodifiable Readable\)|No se puede cambiar la propiedad de familia de fuentes del elemento TextBlock, pero está visible para el localizador.|  
  
|Comentarios de localización de forma libre|Significado|  
|------------------------------------------------|-----------------|  
|$Content \(Trademark\)|El autor de la aplicación indica al localizador que el contenido del elemento TextBlock es una marca comercial.|  
|FontSize \(Trademark font size\)|El autor de la aplicación indica que la propiedad de tamaño de fuente debe respetar el tamaño estándar de la marca comercial.|  
  
### Atributos de localización  
 La información de Localization.Attributes contiene una lista de parejas: el nombre del valor de destino y los valores de localización asociados.  El nombre de destino puede ser un nombre de propiedad o el nombre $Content especial.  Si es un nombre de propiedad, el valor de destino es el valor de la propiedad.  Si es $Content, el valor de destino es el contenido del elemento.  
  
 Hay tres tipos de atributos:  
  
-   **Category**.  Especifica si un valor debe ser modificable en la herramienta de localización.  Vea <xref:System.Windows.LocalizabilityAttribute.Category%2A>.  
  
-   **Readability**.  Especifica si la herramienta de localización podrá leer \(y mostrar\) un valor.  Vea <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.  
  
-   **Modifiability**.  Especifica si la herramienta de localización permite modificar un valor.  Vea <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.  
  
 Estos atributos se pueden especificar en cualquier orden delimitados por espacios.  Si se especifican atributos duplicados, el último invalidará los anteriores.  Por ejemplo, Localization.Attributes \= "Unmodifiable Modifiable" establece la categoría Modifiability en Modifiable porque es el último valor.  
  
 Los atributos Modifiability y Readability no precisan explicación.  El atributo Category proporciona categorías predefinidas que ayudan al localizador al traducir el texto.  Las categorías, tales como Text, Label o Title ofrecen al localizador información sobre cómo traducir el texto.  Hay también categorías especiales: None, Inherit, Ignore y NeverLocalize.  
  
 En la tabla siguiente se muestra el significado de las categorías especiales.  
  
|Categoría|Significado|  
|---------------|-----------------|  
|None|El valor de destino no tiene ninguna categoría definida.|  
|Inherit|El valor de destino hereda su categoría de su elemento primario.|  
|Ignore|El valor de destino se omite en el proceso de localización.  Ignore afecta únicamente al valor actual.  No afecta a los nodos secundarios.|  
|NeverLocalize|El valor actual no se puede localizar.  Los elementos secundarios de un elemento heredan esta categoría.|  
  
<a name="Localization_Comments"></a>   
## Comentarios de localización  
 Localization.Comments contiene cadenas de forma libre acerca del valor de destino.  Los programadores de aplicaciones pueden agregar información para proporcionar sugerencias a los localizadores sobre cómo se debe traducir el texto de las aplicaciones.  El formato de los comentarios puede ser cualquier cadena contenida entre "\(\)".  Utilice '\\' para especificar caracteres de escape.  
  
## Vea también  
 [Globalización de WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)   
 [Usar el diseño automático para crear un botón](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)   
 [Usar una cuadrícula para el diseño automático](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)   
 [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)