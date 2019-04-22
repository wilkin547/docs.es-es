---
title: My.Resources (objeto) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: ee4d30b82ceada5c4f3fc4ad95dc8eeedd9355b0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821743"
---
# <a name="myresources-object"></a>My.Resources (Objeto)
Proporciona propiedades y clases para tener acceso a recursos de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Resources` objeto proporciona acceso a recursos de la aplicación y le permite dinámicamente recupere los recursos de la aplicación. Para obtener más información, consulte [administrar aplicación de recursos (. NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 La `My.Resources` objeto expone sólo recursos globales. No proporciona acceso a los archivos de recursos asociados con los formularios. Debe tener acceso a los recursos de formulario desde el formulario.  
  
 Puede tener acceso a archivos de recursos específicos de la referencia cultural de la aplicación desde el `My.Resources` objeto. De forma predeterminada, el `My.Resources` objeto busca recursos en el archivo de recursos que coincida con la referencia cultural en el <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> propiedad. Sin embargo, puede invalidar este comportamiento y especificar una determinada referencia cultural que se usará para los recursos. Para obtener más información, vea [Resources in Desktop Apps](../../../framework/resources/index.md) (Recursos de aplicaciones de escritorio).  
  
## <a name="properties"></a>Propiedades  
 Las propiedades de la `My.Resources` objeto proporcionar acceso de solo lectura a los recursos de la aplicación. Para agregar o quitar recursos, utilice el **Diseñador de proyectos**. Puede obtener acceso a los recursos agregados a través de la **Diseñador de proyectos** utilizando `My.Resources.` *resourceName*.  
  
 También puede agregar o quitar archivos de recursos, seleccione el proyecto en **el Explorador de soluciones** y haga clic en **Agregar nuevo elemento** o **Agregar elemento existente** desde el  **Proyecto** menú. Puede obtener acceso a los recursos agregados de esta manera mediante `My.Resources.` *NombreArchivoRecursos*`.`*resourceName*.  
  
 Cada recurso tiene un nombre, categoría y valor, y esta configuración de recursos determina cómo aparece en la propiedad para tener acceso al recurso el `My.Resources` objeto. Para los recursos que agregó en el **Diseñador de proyectos**:  
  
-   El nombre determina el nombre de la propiedad,  
  
-   Los datos de recursos están el valor de la propiedad,  
  
-   La categoría determina el tipo de la propiedad:  
  
|Categoría|Propiedad tipo de datos|  
|---|---|  
|**Cadenas**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Imágenes**|<xref:System.Drawing.Bitmap>|  
|**Iconos**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> El <xref:System.IO.UnmanagedMemoryStream> clase se deriva de la <xref:System.IO.Stream> clase, por lo que puede usarse con métodos que toman secuencias, como el <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> método.|  
|**Archivos**|-   [Cadena](../../../visual-basic/language-reference/data-types/string-data-type.md) para archivos de texto.<br />-   <xref:System.Drawing.Bitmap> para los archivos de imagen.<br />-   <xref:System.Drawing.Icon> para los archivos de icono.<br />-   <xref:System.IO.UnmanagedMemoryStream> para los archivos de sonido.|  
|**Otros problemas**|Determinado por la información en el diseñador **tipo** columna.|  
  
## <a name="classes"></a>Clases  
 La `My.Resources` objeto expone cada archivo de recursos como una clase con propiedades compartidas. El nombre de clase es el mismo que el nombre del archivo de recursos. Como se describe en la sección anterior, los recursos en un archivo de recursos se exponen como propiedades en la clase.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece el título de un formulario en el recurso de cadena denominado `Form1Title` en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener una cadena denominada `Form1Title` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece el icono del formulario en el icono denominado `Form1Icon` que se almacena en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener un icono denominado `Form1Icon` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece la imagen de fondo de un formulario en el recurso de imagen denominado `Form1Background`, que se encuentra en el archivo de recursos de la aplicación. Para que funcione este ejemplo, la aplicación debe tener un recurso de imagen denominado `Form1Background` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo reproduce el sonido que se almacena como un recurso de sonido denominado `Form1Greeting` en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener un recurso de sonido denominado `Form1Greeting` en su archivo de recursos. El `My.Computer.Audio.Play` método solo está disponible para las aplicaciones de Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo recupera la versión de la referencia cultural de francés de un recurso de cadena de la aplicación. El recurso se denomina `Message`. Para cambiar la referencia cultural que la `My.Resources` objeto, el ejemplo utiliza <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Para que funcione este ejemplo, la aplicación debe tener una cadena denominada `Message` en su recurso de archivo y la aplicación deben tener la versión de la referencia cultural de francés de ese archivo de recursos, Resources.fr-FR.resx. Si la aplicación no tiene la versión de la referencia cultural de francés del archivo de recursos, la `My.Resource` objeto recupera el recurso desde el archivo de recursos de la referencia cultural predeterminada.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>Vea también

- [Administrar los recursos de la aplicación (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Recursos de aplicaciones de escritorio](../../../framework/resources/index.md)
