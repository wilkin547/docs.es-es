---
title: Procedimiento Agregar un tipo de propietario para una propiedad de dependencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 1b1f2b241868b02e430af82bac8e9f6a617e511b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217099"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Procedimiento Agregar un tipo de propietario para una propiedad de dependencia
En este ejemplo se muestra cómo agregar una clase como un propietario de una propiedad de dependencia registrada para un tipo diferente. Al hacerlo, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lector y el sistema de propiedades son ambos puede reconocer la clase como un propietario de la propiedad adicional. Agregar como propietario, opcionalmente, permite que la clase que se agrega proporcionar metadatos específicos del tipo.  
  
 En el ejemplo siguiente, `StateProperty` se registra una propiedad por la `MyStateControl` clase. La clase `UnrelatedStateControl` agrega como propietario de la `StateProperty` utilizando el <xref:System.Windows.DependencyProperty.AddOwner%2A> método, específicamente con la firma que permite nuevos metadatos para la propiedad de dependencia tal como existe en el tipo de adición. Tenga en cuenta que se debe proporcionar [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] descriptores de acceso para la propiedad similar del ejemplo se muestra en el [implementar una propiedad de dependencia](how-to-implement-a-dependency-property.md) ejemplo, así como volver a exponer el identificador de propiedad de dependencia en la clase que se va a agregar como propietario.  
  
 Sin contenedores, la propiedad de dependencia seguiría funcionando desde la perspectiva de acceso mediante programación utilizando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Pero normalmente desea este comportamiento del sistema de propiedades con en paralelo el [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] contenedores de propiedad. Los contenedores que sea más fácil establecer la propiedad de dependencia mediante programación y permiten establecer las propiedades como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributos.  
  
 Para obtener información sobre cómo invalidar los metadatos predeterminados, consulte [invalidar metadatos en una propiedad de dependencia](how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vea también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
