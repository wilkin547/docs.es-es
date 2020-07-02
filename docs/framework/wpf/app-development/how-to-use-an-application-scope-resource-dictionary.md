---
title: 'Cómo: Usar un diccionario de recursos en el ámbito de aplicación'
description: Obtenga información sobre cómo definir y usar un diccionario de recursos personalizado de ámbito de aplicación en Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 9d117dea6c554339b4b462b9bf37b80da2dc477f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613714"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Cómo: Usar un diccionario de recursos en el ámbito de aplicación
En este ejemplo se muestra cómo definir y usar un diccionario de recursos personalizado de ámbito de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 <xref:System.Windows.Application>expone un almacén de ámbito de aplicación para los recursos compartidos: <xref:System.Windows.Application.Resources%2A> . De forma predeterminada, la <xref:System.Windows.Application.Resources%2A> propiedad se inicializa con una instancia del <xref:System.Windows.ResourceDictionary> tipo. Esta instancia se utiliza al obtener y establecer las propiedades del ámbito de aplicación mediante <xref:System.Windows.Application.Resources%2A> . Para obtener más información, consulte [Cómo: obtener y establecer un recurso de ámbito de aplicación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Si tiene varios recursos que establece con <xref:System.Windows.Application.Resources%2A> , puede usar un diccionario de recursos personalizado para almacenar esos recursos y establecerlos en <xref:System.Windows.Application.Resources%2A> su lugar. A continuación se muestra cómo declarar un diccionario de recursos personalizado mediante XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 El intercambio de diccionarios de recursos completos mediante <xref:System.Windows.Application.Resources%2A> le permite admitir los temas del ámbito de aplicación, donde cada tema está encapsulado por un único Diccionario de recursos. En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 A continuación se muestra cómo puede obtener recursos del ámbito de aplicación del Diccionario de recursos expuesto por <xref:System.Windows.Application.Resources%2A> en XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 A continuación, se muestra cómo puede obtener también los recursos en el código.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Hay dos consideraciones que se deben tener en cuenta al usar <xref:System.Windows.Application.Resources%2A> . En primer lugar, la *clave* del diccionario es un objeto, por lo que debe usar exactamente la misma instancia de objeto cuando ambos establecen y obtienen un valor de propiedad. (Tenga en cuenta que la clave distingue entre mayúsculas y minúsculas cuando se usa una cadena). En segundo lugar, el *valor* del diccionario es un objeto, por lo que tendrá que convertir el valor al tipo deseado al obtener un valor de propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Diccionarios de recursos combinados](../advanced/merged-resource-dictionaries.md)
