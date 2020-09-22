---
title: My.Resources (Objeto)
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 3d12524706f680434d5b6d8da39c89042bea3281
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867330"
---
# <a name="myresources-object"></a>My.Resources (Objeto)

Proporciona propiedades y clases para tener acceso a los recursos de la aplicación.  
  
## <a name="remarks"></a>Comentarios  

 El `My.Resources` objeto proporciona acceso a los recursos de la aplicación y permite recuperar dinámicamente los recursos de la aplicación. Para obtener más información, vea [administrar recursos de aplicación (.net)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 El objeto `My.Resources` expone solo recursos globales. No da acceso a los archivos de recursos asociados a los formularios. Para acceder a los recursos de formulario, hay que hacerlo desde el formulario.  
  
 Puede tener acceso a los archivos de recursos específicos de la referencia cultural de la aplicación desde el `My.Resources` objeto. De forma predeterminada, el `My.Resources` objeto busca recursos del archivo de recursos que coincida con la referencia cultural de la <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> propiedad. Sin embargo, puede invalidar este comportamiento y especificar una referencia cultural determinada que se usará para los recursos. Para obtener más información, vea [Recursos en aplicaciones .NET](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Propiedades  

 Las propiedades del `My.Resources` objeto proporcionan acceso de solo lectura a los recursos de la aplicación. Para agregar o quitar recursos, use el **Diseñador de proyectos**. Puede tener acceso a los recursos agregados a través del **Diseñador de proyectos** mediante `My.Resources.` *resourceName*.  
  
 También puede Agregar o quitar archivos de recursos seleccionando el proyecto en **Explorador de soluciones** y haciendo clic en **Agregar nuevo elemento** o **Agregar elemento existente** en el menú **proyecto** . Puede tener acceso a los recursos agregados de esta manera mediante `My.Resources.` *nombrearchivorecursos* `.` *resourceName*.  
  
 Cada recurso tiene un nombre, una categoría y un valor, y esta configuración de recursos determina el modo en que la propiedad para tener acceso al recurso aparece en el `My.Resources` objeto. Para los recursos agregados en el **Diseñador de proyectos**:  
  
- El nombre determina el nombre de la propiedad.  
  
- Los datos del recurso son el valor de la propiedad.  
  
- La categoría determina el tipo de la propiedad:  
  
|Category|Tipo de datos de la propiedad|  
|---|---|  
|**Cadenas**|[String](../data-types/string-data-type.md)|  
|**Imágenes**|<xref:System.Drawing.Bitmap>|  
|**Iconos**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> La <xref:System.IO.UnmanagedMemoryStream> clase se deriva de la <xref:System.IO.Stream> clase, por lo que se puede utilizar con métodos que toman secuencias, como el <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> método.|  
|**Archivos**|-   [Cadena](../data-types/string-data-type.md) para los archivos de texto.<br />-   <xref:System.Drawing.Bitmap> para los archivos de imagen.<br />-   <xref:System.Drawing.Icon> para los archivos de icono.<br />-   <xref:System.IO.UnmanagedMemoryStream> para archivos de sonido.|  
|**Otros**|Lo determina la información de la columna de **tipo** del diseñador.|  
  
## <a name="classes"></a>Clases  

 El `My.Resources` objeto expone cada archivo de recursos como una clase con propiedades compartidas. El nombre de clase es el mismo que el nombre del archivo de recursos. Como se describe en la sección anterior, los recursos de un archivo de recursos se exponen como propiedades en la clase.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se establece el título de un formulario en el recurso de cadena denominado `Form1Title` en el archivo de recursos de la aplicación. Para que el ejemplo funcione, la aplicación debe tener una cadena denominada `Form1Title` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se establece el icono del formulario en el icono denominado `Form1Icon` que está almacenado en el archivo de recursos de la aplicación. Para que el ejemplo funcione, la aplicación debe tener un icono denominado `Form1Icon` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se establece la imagen de fondo de un formulario en el recurso de imagen denominado `Form1Background` , que se encuentra en el archivo de recursos de la aplicación. Para que este ejemplo funcione, la aplicación debe tener un recurso de imagen denominado `Form1Background` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se reproduce el sonido que se almacena como un recurso de audio denominado `Form1Greeting` en el archivo de recursos de la aplicación. Para que el ejemplo funcione, la aplicación debe tener un recurso de audio denominado `Form1Greeting` en su archivo de recursos. El `My.Computer.Audio.Play` método solo está disponible para aplicaciones Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se recupera la versión de la referencia cultural francesa de un recurso de cadena de la aplicación. El recurso se denomina `Message` . Para cambiar la referencia cultural que `My.Resources` utiliza el objeto, en el ejemplo se utiliza <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> .  
  
 Para que este ejemplo funcione, la aplicación debe tener una cadena denominada `Message` en su archivo de recursos y la aplicación debe tener la versión de referencia cultural en francés de ese archivo de recursos, Resources.fr-fr. resx. Si la aplicación no tiene la versión de referencia cultural en francés del archivo de recursos, el `My.Resource` objeto recupera el recurso del archivo de recursos de referencia cultural predeterminada.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>Consulte también

- [Administrar los recursos de la aplicación (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Recursos de aplicaciones de escritorio](../../../framework/resources/index.md)
