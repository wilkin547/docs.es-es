---
title: 'Cómo: Usar recursos en aplicaciones localizables'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212480"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>Cómo: usar recursos en aplicaciones localizables

La localización significa adaptar una interfaz de usuario a diferentes referencias culturales. Para ello, se debe traducir el texto, como títulos, leyendas y elementos del cuadro de lista. Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos. Consulte [localizar una aplicación](how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para la localización. Para que una aplicación WPF sea localizable, los desarrolladores deben compilar todos los recursos localizables en un ensamblado de recursos. El ensamblado de recursos se localiza en idiomas diferentes y el código subyacente usa la API de administración de recursos para cargar.

## <a name="example"></a>Ejemplo

Uno de los archivos necesarios para una aplicación WPF es un archivo de proyecto (. proj). Todos los recursos que se utilizan en la aplicación deben incluirse en el archivo de proyecto. En el siguiente ejemplo de XAML se muestra esto.

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

Para usar un recurso en la aplicación, cree una instancia <xref:System.Resources.ResourceManager> y cargue el recurso que desea usar. En el siguiente código de C# se muestra cómo hacerlo.

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>Consulte también

- [Localizar una aplicación](how-to-localize-an-application.md)
