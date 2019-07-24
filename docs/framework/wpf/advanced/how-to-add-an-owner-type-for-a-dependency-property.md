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
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401134"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Procedimiento Agregar un tipo de propietario para una propiedad de dependencia
En este ejemplo se muestra cómo agregar una clase como propietario de una propiedad de dependencia registrada para un tipo diferente. Al hacerlo, el lector [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sistema de propiedades pueden reconocer la clase como propietario adicional de la propiedad. Agregar como propietario permite opcionalmente agregar la clase para proporcionar metadatos específicos del tipo.  
  
 En el ejemplo siguiente, `StateProperty` es una propiedad registrada por la `MyStateControl` clase. La clase `UnrelatedStateControl` se agrega a sí misma como propietario `StateProperty` de mediante <xref:System.Windows.DependencyProperty.AddOwner%2A> el método, específicamente utilizando la firma que permite nuevos metadatos para la propiedad de dependencia tal como existe en el tipo de adición. Tenga en cuenta que debe proporcionar descriptores de acceso Common Language Runtime (CLR) para la propiedad similar al ejemplo que se muestra en el ejemplo de [implementación de una propiedad de dependencia](how-to-implement-a-dependency-property.md) , así como volver a exponer el identificador de la propiedad de dependencia en la clase que se va a agregar como propietario.  
  
 Sin contenedores, la propiedad de dependencia seguiría funcionando desde la perspectiva del acceso mediante programación <xref:System.Windows.DependencyObject.GetValue%2A> mediante <xref:System.Windows.DependencyObject.SetValue%2A>o. Pero normalmente desea enlazar este comportamiento del sistema de propiedades con los contenedores de propiedades de CLR. Los contenedores facilitan el establecimiento de la propiedad de dependencia mediante programación y permiten establecer las propiedades como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributos.  
  
 Para obtener información sobre cómo invalidar los metadatos predeterminados, vea [invalidar metadatos para una propiedad de dependencia](how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vea también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
