---
title: 'Cómo: Agregar un tipo de propietario para una propiedad de dependencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: bf3f73743d1c76145bf520ed859c27c4d3aaf662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>Cómo: Agregar un tipo de propietario para una propiedad de dependencia
Este ejemplo muestra cómo agregar una clase como un propietario de una propiedad de dependencia que se registra para un tipo diferente. Al hacerlo, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lector y el sistema de propiedades son ambos capaz de reconocer la clase como un propietario adicional de la propiedad. Agregar como propietario, opcionalmente, permite la adición de la clase proporcionar metadatos específicos del tipo.  
  
 En el ejemplo siguiente, `StateProperty` es una propiedad registrada por la `MyStateControl` clase. La clase `UnrelatedStateControl` agrega como un propietario de la `StateProperty` mediante el <xref:System.Windows.DependencyProperty.AddOwner%2A> método concreto mediante la firma que permite utilizar nuevos metadatos para la propiedad de dependencia tal como existe en el tipo de adición. Tenga en cuenta que debe proporcionar [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] descriptores de acceso de la propiedad similar al ejemplo mostrado en el [implementar una propiedad de dependencia](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) ejemplo, así como volver a exponer el identificador de la propiedad de dependencia en la clase que se va a agregar como propietario.  
  
 Sin contenedores, la propiedad de dependencia seguiría funcionando desde la perspectiva de acceso mediante programación utilizando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>. Pero suele ser conveniente imitar este comportamiento del sistema de propiedades con el [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] contenedores de propiedad. Los contenedores que resulten más fáciles de establecer la propiedad de dependencia mediante programación y le permite establecer las propiedades como [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributos.  
  
 Para obtener más información sobre cómo invalidar los metadatos predeterminados, consulte [invalidar metadatos para una propiedad de dependencia](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
