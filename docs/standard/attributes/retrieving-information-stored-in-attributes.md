---
title: "Recuperar información almacenada en atributos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a>Recuperar información almacenada en atributos
La recuperación de un atributo personalizado es un proceso sencillo. En primer lugar, declare una instancia del atributo que van a recuperar. A continuación, utilice el <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> método para inicializar el atributo nuevo en el valor del atributo que van a recuperar. Una vez inicializado el nuevo atributo, basta con usar sus propiedades para obtener los valores.  
  
> [!IMPORTANT]
>  En este tema se describe cómo recuperar los atributos para el código que se cargan en el contexto de ejecución. Para recuperar los atributos del código que se cargan en el contexto de solo reflexión, debe utilizar el <xref:System.Reflection.CustomAttributeData> clase, como se muestra en [Cómo: cargar ensamblados en el contexto de only](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 En esta sección se describe los siguientes métodos para recuperar atributos:  
  
-   [Recuperar una sola instancia de un atributo](#cpconretrievingsingleinstanceofattribute)  
  
-   [Recuperar varias instancias de un atributo aplicadas al mismo ámbito](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Recuperar varias instancias de un atributo aplicadas a ámbitos diferentes](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>Recuperar una sola instancia de un atributo  
 En el ejemplo siguiente, la `DeveloperAttribute` (que se describe en la sección anterior) se aplica a la `MainApp` clase en el nivel de clase. El `GetAttribute` método usa **GetCustomAttribute** para recuperar los valores almacenados en `DeveloperAttribute` en el nivel de clase antes de mostrarlos en la consola.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Este programa muestra el texto siguiente cuando se ejecuta.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Si no se encuentra el atributo, el **GetCustomAttribute** método inicializa `MyAttribute` con un valor null. Este ejemplo se comprueba `MyAttribute` para esta instancia y notifica al usuario si no se encuentra ningún atributo. Si el `DeveloperAttribute` no se encuentra en el ámbito de clase, aparece el siguiente mensaje en la consola.  
  
```  
The attribute was not found.   
```  
  
 En este ejemplo se da por supuesto que la definición de atributo está en el espacio de nombres actual. No olvide importar el espacio de nombres en el que reside la definición de atributo si no está en el espacio de nombres actual.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>Recuperar varias instancias de un atributo aplicadas al mismo ámbito  
 En el ejemplo anterior, se pasan a la clase para inspeccionar y el atributo específico para buscar <xref:System.Attribute.GetCustomAttribute%2A>. Ese código funciona bien si solo una instancia de un atributo se aplica en el nivel de clase. Sin embargo, si se aplican varias instancias de un atributo en el mismo nivel de clase, el **GetCustomAttribute** método no recupera toda la información. En casos donde se aplican varias instancias del mismo atributo al mismo ámbito, puede usar <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> para colocar todas las instancias de un atributo en una matriz. Por ejemplo, si dos instancias de `DeveloperAttribute` se aplican en el nivel de clase de la misma clase, el `GetAttribute` método se puede modificar para mostrar la información encontrada en ambos atributos. Recuerde que, para aplicar varios atributos en el mismo nivel, el atributo debe definirse con la **AllowMultiple** propiedad establecida en **true** en el <xref:System.AttributeUsageAttribute>.  
  
 En el ejemplo de código siguiente se muestra cómo utilizar el **GetCustomAttributes** método para crear una matriz que hace referencia a todas las instancias de `DeveloperAttribute` en cualquier determinada clase. Los valores de todos los atributos, a continuación, se muestran en la consola.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Si no se encuentra ningún atributo, este código avisa al usuario. En caso contrario, la información contenida en ambas instancias de `DeveloperAttribute` se muestra.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>Recuperar varias instancias de un atributo aplicadas a ámbitos diferentes  
 El <xref:System.Attribute.GetCustomAttributes%2A> y <xref:System.Attribute.GetCustomAttribute%2A> métodos no buscan una clase completa y devuelven todas las instancias de un atributo de esa clase. En su lugar, buscan solo un método especificado o un miembro a la vez. Si tiene una clase con el mismo atributo aplicado a todos los miembros y desea recuperar los valores de todos los atributos aplicados a dichos miembros, debe proporcionar cada método o miembro individualmente a **GetCustomAttributes** y  **GetCustomAttribute**.  
  
 En el ejemplo de código siguiente se toma una clase como parámetro y busca el `DeveloperAttribute` (definido previamente) en el nivel de clase y en todos los métodos individuales de esa clase.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Si no hay instancias de la `DeveloperAttribute` se encuentran en el nivel de método o nivel de clase, el `GetAttribute` método notifica al usuario que no se encontraron atributos y muestra el nombre del método o clase que no contiene el atributo. Si se encuentra un atributo, el `Name`, `Level`, y `Reviewed` campos se muestran en la consola.  
  
 Puede utilizar los miembros de la <xref:System.Type> clase para obtener los miembros y métodos individuales de la clase pasada como parámetro. Este ejemplo se consulta primero el **tipo** objeto que se va a obtener información de atributos para el nivel de clase. A continuación, se utiliza <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> para colocar instancias de todos los métodos en una matriz de <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objetos que se va a recuperar información de atributos para el nivel de método. También puede usar el <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> método para comprobar si los atributos en el nivel de propiedad o <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> para comprobar si los atributos en el nivel de constructor.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [Atributos](../../../docs/standard/attributes/index.md)
