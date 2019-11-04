---
title: 'Cómo: Usar recursos de aplicaciones'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460271"
---
# <a name="how-to-use-application-resources"></a>Cómo: Usar recursos de aplicaciones
En este ejemplo se muestra cómo usar recursos de aplicaciones.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra un archivo de definición de aplicación. El archivo de definición de aplicación define una sección de recursos (un valor para la propiedad <xref:System.Windows.Application.Resources%2A>). Todas las demás páginas que forman parte de la aplicación pueden obtener acceso a los recursos definidos en el nivel de aplicación. En este caso, el recurso es un estilo declarado. Dado que un estilo completo que incluye una plantilla de control puede ser largo, en este ejemplo se omite la plantilla de control que se define dentro del <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> establecedor de la propiedad del estilo.  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 En el ejemplo siguiente se muestra una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página que hace referencia al recurso de nivel de aplicación que se ha definido en el ejemplo anterior. Se hace referencia al recurso mediante una [extensión de marcado StaticResource](staticresource-markup-extension.md) que especifica la clave de recurso única para el recurso solicitado. No se encontró ningún recurso con la clave "GelButton" en la página actual, por lo que el ámbito de búsqueda de recursos para el recurso solicitado continúa más allá de la página actual y en los recursos de nivel de aplicación definidos.  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Información general sobre la administración de aplicaciones](../app-development/application-management-overview.md)
- [Temas "Cómo..."](resources-how-to-topics.md)
