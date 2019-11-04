---
title: 'Cómo: Usar un diccionario de recursos en el ámbito de aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459798"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Cómo: Usar un diccionario de recursos en el ámbito de aplicación
En este ejemplo se muestra cómo definir y usar un diccionario de recursos personalizado de ámbito de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 <xref:System.Windows.Application> expone un almacén de ámbito de aplicación para los recursos compartidos: <xref:System.Windows.Application.Resources%2A>. De forma predeterminada, la propiedad <xref:System.Windows.Application.Resources%2A> se inicializa con una instancia del tipo <xref:System.Windows.ResourceDictionary>. Esta instancia se utiliza al obtener y establecer las propiedades del ámbito de aplicación mediante <xref:System.Windows.Application.Resources%2A>. Para obtener más información, consulte [Cómo: obtener y establecer un recurso de ámbito de aplicación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Si tiene varios recursos que establece mediante <xref:System.Windows.Application.Resources%2A>, puede usar un diccionario de recursos personalizado para almacenar esos recursos y establecer <xref:System.Windows.Application.Resources%2A> con él en su lugar. A continuación se muestra cómo declarar un diccionario de recursos personalizado mediante XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 El intercambio de diccionarios de recursos completos con <xref:System.Windows.Application.Resources%2A> permite admitir temas del ámbito de aplicación, donde cada tema se encapsula mediante un único Diccionario de recursos. En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 A continuación se muestra cómo puede obtener recursos del ámbito de aplicación del Diccionario de recursos expuesto por <xref:System.Windows.Application.Resources%2A> en XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 A continuación, se muestra cómo puede obtener también los recursos en el código.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Hay dos consideraciones que se deben tener en cuenta al utilizar <xref:System.Windows.Application.Resources%2A>. En primer lugar, la *clave* del diccionario es un objeto, por lo que debe usar exactamente la misma instancia de objeto cuando ambos establecen y obtienen un valor de propiedad. (Tenga en cuenta que la clave distingue entre mayúsculas y minúsculas cuando se usa una cadena). En segundo lugar, el *valor* del diccionario es un objeto, por lo que tendrá que convertir el valor al tipo deseado al obtener un valor de propiedad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Diccionarios de recursos combinados](../advanced/merged-resource-dictionaries.md)
