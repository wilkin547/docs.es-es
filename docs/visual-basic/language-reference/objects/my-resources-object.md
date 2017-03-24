---
title: My.Resources (objeto) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6ad5bd4e33438256719b59cb0936cf6bc8525ab1
ms.lasthandoff: 03/13/2017

---
# <a name="myresources-object"></a>My.Resources (Objeto)
Proporciona propiedades y clases para tener acceso a recursos de la aplicación.  
  
## <a name="remarks"></a>Comentarios  
 La `My.Resources` objeto proporciona acceso a recursos de la aplicación y le permite dinámicamente recupere los recursos de la aplicación. Para obtener más información, consulte [administración de recursos (. NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).  
  
 La `My.Resources` objeto expone sólo recursos globales. No proporciona acceso a los archivos de recursos asociados con los formularios. Debe tener acceso a los recursos de formulario desde el formulario. Para obtener más información, consulte [Tutorial: Adaptar Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).  
  
 Puede tener acceso a archivos de recursos específicos de la referencia cultural de la aplicación desde el `My.Resources` objeto. De forma predeterminada, el `My.Resources` objeto busca los recursos del archivo de recursos que coincide con la referencia cultural en el <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>propiedad.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> Sin embargo, puede invalidar este comportamiento y especificar una referencia cultural determinada que se utilizará para los recursos. Para obtener más información, consulte [recursos en aplicaciones de escritorio](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890).  
  
## <a name="properties"></a>Propiedades  
 Las propiedades de la `My.Resources` el objeto proporciona acceso de sólo lectura a los recursos de la aplicación. Para agregar o quitar recursos, utilice la **Project Designer**. Para obtener más información, consulte [Cómo: agregar o quitar recursos](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Puede tener acceso a los recursos agregados a través de la **Project Designer** utilizando `My.Resources.``resourceName`.  
  
 También puede agregar o quitar archivos de recursos seleccionando el proyecto en **el Explorador de soluciones** y haga clic en **Agregar nuevo elemento** o **Agregar elemento existente** desde el **proyecto** menú. Puede tener acceso a los recursos agregados de esta manera mediante `My.Resources.``resourceFileName`.`resourceName`.  
  
 Cada recurso tiene un nombre, categoría y valor, y estos valores de recurso determinan cómo aparece la propiedad para tener acceso al recurso en el `My.Resources` objeto. Para los recursos agregados en el **Project Designer**:  
  
-   El nombre determina el nombre de la propiedad  
  
-   Los datos del recurso están el valor de la propiedad  
  
-   La categoría determina el tipo de la propiedad:  
  
|Categoría|Tipo de datos de propiedad|  
|---|---|  
|**Cadenas**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Imágenes**|<xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap>|  
|**Iconos**|<xref:System.Drawing.Icon></xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream><br /><br /> La <xref:System.IO.UnmanagedMemoryStream>clase se deriva de la <xref:System.IO.Stream>clase, de manera que se puede utilizar con métodos que toman secuencias, como el <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>método.</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream>|  
|**Archivos**|-   [Cadena](../../../visual-basic/language-reference/data-types/string-data-type.md) de archivos de texto.<br />- <xref:System.Drawing.Bitmap>para archivos de imagen.</xref:System.Drawing.Bitmap><br />- <xref:System.Drawing.Icon>para archivos de icono.</xref:System.Drawing.Icon><br />- <xref:System.IO.UnmanagedMemoryStream>para archivos de sonido.</xref:System.IO.UnmanagedMemoryStream>|  
|**Otros problemas**|Determinado por la información en el diseñador **tipo** columna.|  
  
## <a name="classes"></a>Clases  
 La `My.Resources` objeto expone cada archivo de recursos como una clase con propiedades compartidas. El nombre de clase es el mismo que el nombre del archivo de recursos. Como se describe en la sección anterior, los recursos en un archivo de recursos se exponen como propiedades en la clase.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece el título de un formulario en el recurso de cadena denominado `Form1Title` en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener una cadena denominada `Form1Title` en su archivo de recursos. Para obtener más información, consulte [Cómo: agregar o quitar recursos](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).  
  
 [!code-vb[1 VbVbalrMyResources](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece el icono del formulario en el icono denominado `Form1Icon` que se almacena en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener un icono denominado `Form1Icon` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources&#2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo establece la imagen de fondo de un formulario en el recurso de imagen denominado `Form1Background`, que está en el archivo de recursos de la aplicación. Para que funcione este ejemplo, la aplicación debe tener un recurso de imagen denominado `Form1Background` en su archivo de recursos.  
  
 [!code-vb[VbVbalrMyResources&3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo reproduce el sonido que se almacena como un recurso de sonido denominado `Form1Greeting` en el archivo de recursos de la aplicación. Para que funcione el ejemplo, la aplicación debe tener un recurso de sonido denominado `Form1Greeting` en su archivo de recursos. El `My.Computer.Audio.Play` método solo está disponible para aplicaciones de Windows Forms.  
  
 [!code-vb[VbVbalrMyResources Nº&4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo recupera la versión de la referencia cultural francés de un recurso de cadena de la aplicación. El recurso se denomina `Message`. Para cambiar la referencia cultural que el `My.Resources` objeto, el ejemplo utiliza <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>  
  
 Para que funcione este ejemplo, la aplicación debe tener una cadena denominada `Message` en su recurso de archivo y la aplicación deben tener la versión de referencia cultural francesa de ese archivo de recursos, Resources.fr-FR.resx. Para obtener más información, consulte [Cómo: agregar o quitar recursos](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d). Si la aplicación no tiene la versión de la referencia cultural Francés del archivo de recursos, la `My.Resource` objeto recupera el recurso del archivo de recursos de referencia cultural predeterminada.  
  
 [!code-vb[VbVbalrMyResources&#10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Cómo: agregar o quitar recursos](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)   
 [Administración de recursos de aplicación (. NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)   
 [Recursos en aplicaciones de escritorio](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)   
 [Tutorial: Adaptar formularios Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)
