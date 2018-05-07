---
title: 'Cómo: Usar recursos de aplicaciones'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: 4305c49c4322d164e2481c1508dda7c038c14694
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-application-resources"></a>Cómo: Usar recursos de aplicaciones
En este ejemplo se muestra cómo usar recursos de aplicaciones.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra un archivo de definición de aplicación. El archivo de definición de aplicación define una sección de recursos (un valor para el <xref:System.Windows.Application.Resources%2A> propiedad). Todas las demás páginas que forman parte de la aplicación pueden obtener acceso a los recursos definidos en el nivel de aplicación. En este caso, el recurso es un estilo declarado. Dado que un estilo completo que incluye una plantilla de control puede ser bastante largo, este ejemplo omite la plantilla de control que se define en el <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> establecedor de propiedad del estilo.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 El ejemplo siguiente muestra un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página que hace referencia al recurso de nivel de aplicación definido en el ejemplo anterior. El recurso se hace referencia mediante un [extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) que especifica la clave de recurso único para el recurso solicitado. No se encontró ningún recurso con la clave "GelButton" en la página actual, por lo que el ámbito de búsqueda de recursos para el recurso solicitado continúa más allá de la página actual y en los recursos de nivel de aplicación definidos.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
