---
title: Atributos y comentarios sobre localización
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF], attributes
- localization [WPF], comments
ms.assetid: ead2d9ac-b709-4ec1-a924-39927a29d02f
ms.openlocfilehash: 7281ca6d76f0d2ffb5020feba236b4e4cf948bdd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141593"
---
# <a name="localization-attributes-and-comments"></a>Atributos y comentarios sobre localización
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]los comentarios de localización son propiedades, dentro del código fuente XAML, proporcionadas por los desarrolladores para proporcionar reglas y sugerencias para la localización. Los comentarios de localización de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] contienen dos conjuntos de información: atributos de localizabilidad y comentarios de localización de forma libre. Los atributos de localización se usan en la API de localización de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para indicar qué recursos se van a localizar. Los comentarios de forma libre son cualquier información que el autor de la aplicación quiera incluir.  

<a name="Localizer_Comments_"></a>
## <a name="localization-comments"></a>Comentarios de localización  
 Si los autores de aplicaciones de marcado tienen requisitos para elementos específicos en XAML, como restricciones en la longitud del texto, la familia de fuentes o el tamaño de fuente, pueden transmitir esta información a los localizadores con comentarios en el código XAML. El proceso para agregar comentarios al código fuente es el siguiente:  
  
1. El desarrollador de aplicaciones agrega comentarios de localización al código fuente XAML.  
  
2. Durante el proceso de compilación, puede especificar en el archivo .proj si quiere dejar comentarios de localización de forma libre en el ensamblado, quitar parte de los comentarios o quitarlos todos. Los comentarios eliminados se colocan en un archivo independiente. Especifique la opción mediante una etiqueta `LocalizationDirectivesToLocFile`; p. ej.:  
  
     `<LocalizationDirectivesToLocFile>`*valor*`</LocalizationDirectivesToLocFile>`  
  
3. Los valores que se pueden asignar son:  
  
    - **None**: los comentarios y atributos permanecen dentro del ensamblado y no se genera ningún archivo independiente.  
  
    - **CommentsOnly**: elimina solo los comentarios del ensamblado y los coloca en el archivo LocFile independiente.  
  
    - **All**: quita los comentarios y los atributos del ensamblado y los coloca en un archivo LocFile independiente.  
  
4. Cuando se extraen recursos localizables de BAML, la API de localización de BAML respeta los atributos de localizabilidad.  
  
5. Los archivos de comentarios de localización, que contienen solo comentarios de forma libre, se incorporan al proceso de localización en un momento posterior.  
  
 En el ejemplo siguiente se muestra cómo agregar comentarios de localización a un archivo XAML.  
  
 `<TextBlock x:Id = "text01"`  
  
 `FontFamily = "Microsoft Sans Serif"`  
  
 `FontSize = "12"`  
  
 `Localization.Attributes = "$Content (Unmodifiable Readable Text)`  
  
 `FontFamily (Unmodifiable Readable)"`  
  
 `Localization.Comments = "$Content (Trademark)`  
  
 `FontSize (Trademark font size)" >`  
  
 `Microsoft`  
  
 `</TextBlock>`  
  
 En el ejemplo anterior, la sección Localization.Attributes contiene los atributos de localización, y la sección Localization.Comments, los comentarios de forma libre. En las siguientes tablas se muestran los atributos y comentarios y su significado para el localizador.  
  
|Atributos de localización|Significado|  
|-----------------------------|-------------|  
|$Content (texto legible no modificable)|No se puede modificar el contenido del elemento TextBlock. Los localizadores no pueden cambiar la palabra "Microsoft". El contenido es visible (legible) para el localizador. La categoría del contenido es texto.|  
|FontFamily (legible no modificable)|No se puede cambiar la propiedad de la familia de fuentes del elemento TextBlock, pero está visible para el localizador.|  
  
|Comentarios de localización de forma libre|Significado|  
|--------------------------------------|-------------|  
|$Content (marca)|El autor de la aplicación indica al localizador que el contenido del elemento TextBlock es una marca registrada.|  
|FontSize (tamaño de fuente de marca comercial)|El autor de la aplicación indica que la propiedad de tamaño de fuente debe seguir el tamaño de la marca comercial.|  
  
### <a name="localizability-attributes"></a>Atributos de localizabilidad  
 La información de Localization.Attributes contiene una lista de pares: el nombre del valor de destino y los valores de localizabilidad asociados. El nombre de destino puede ser un nombre de propiedad o el nombre $Content especial. Si es un nombre de propiedad, el valor de destino es el valor de la propiedad. Si es $Content, el valor de destino es el contenido del elemento.  
  
 Hay tres tipos de atributo:  
  
- **Categoría**. Especifica si un valor debe ser modificable desde una herramienta de localización. Vea <xref:System.Windows.LocalizabilityAttribute.Category%2A>.  
  
- **Legibilidad**. Especifica si la herramienta de localización podrá leer (y mostrar) un valor. Vea <xref:System.Windows.LocalizabilityAttribute.Readability%2A>.  
  
- **Modificabilidad**. Especifica si un valor debe ser modificable desde una herramienta de localización. Vea <xref:System.Windows.LocalizabilityAttribute.Modifiability%2A>.  
  
 Estos atributos se pueden especificar en cualquier orden delimitado por un espacio. En caso de que se especifiquen atributos duplicados, el último atributo invalidará los anteriores. Por ejemplo, Localization.Attributes = "Unmodifiable Modifiable" define el atributo Modificabilidad como Modificable porque es el último valor.  
  
 La modificabilidad y la legibilidad no necesitan explicación. El atributo Categoría proporciona categorías predefinidas que ayudan al localizador al traducir el texto. Las categorías, como Text, Label o Title, ofrecen al localizador información sobre cómo traducir el texto. También hay categorías especiales: None, Inherit, Ignore y NeverLocalize.  
  
 En la tabla siguiente se muestra el significado de las categorías especiales.  
  
|Category|Significado|  
|--------------|-------------|  
|None|El valor de destino no tiene ninguna categoría definida.|  
|Heredar|El valor de destino hereda su categoría de su elemento primario.|  
|Ignore|El valor de destino se omite en el proceso de localización. Ignore solo afecta al valor actual. No afecta a los nodos secundarios.|  
|NeverLocalize|No se puede localizar el valor actual. Los elementos secundarios de un elemento heredan esta categoría.|  
  
<a name="Localization_Comments"></a>
## <a name="localization-comments"></a>Comentarios de localización  
 Localization.Comments contiene cadenas con formato libre sobre el valor de destino. Los desarrolladores de aplicaciones pueden agregar información para proporcionar a los localizadores sugerencias sobre cómo se debe traducir el texto de las aplicaciones. El formato de los comentarios puede ser cualquier cadena entre "()". Use "\\" para crear caracteres de escape.  
  
## <a name="see-also"></a>Consulte también

- [Globalización de WPF](globalization-for-wpf.md)
- [Usar el diseño automático para crear un botón](how-to-use-automatic-layout-to-create-a-button.md)
- [Usar una cuadrícula para el diseño automático](how-to-use-a-grid-for-automatic-layout.md)
- [Localizar una solicitud](how-to-localize-an-application.md)
