---
title: "Recuperar informaci&#243;n almacenada en atributos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "atributos [.NET Framework], recuperar"
  - "instancias de atributos múltiples"
  - "recuperar atributos"
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Recuperar informaci&#243;n almacenada en atributos
La recuperación de un atributo personalizado es un proceso simple.  En primer lugar, se ha de declarar una instancia del atributo que se desee recuperar.  A continuación, utilice el método <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> para inicializar el atributo nuevo en el valor del atributo que se desee recuperar.  Una vez inicializado el atributo nuevo, basta con utilizar sus propiedades para obtener los valores.  
  
> [!IMPORTANT]
>  Este tema describe cómo recuperar los atributos de código cargado en el contexto de ejecución.  Con el fin de recuperar atributos para código cargado en el contexto de sólo reflexión, debe utilizar la clase <xref:System.Reflection.CustomAttributeData>, como se muestra en [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
 Esta sección describe los métodos siguientes para recuperar atributos:  
  
-   [Recuperar una sola instancia de un atributo](#cpconretrievingsingleinstanceofattribute)  
  
-   [Recuperar varias instancias de un atributo aplicadas al mismo ámbito](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [Recuperar varias instancias de un atributo aplicadas a ámbitos diferentes](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## Recuperar una sola instancia de un atributo  
 En el ejemplo siguiente, el atributo `DeveloperAttribute` \(descrito en la sección anterior\) se aplica a la clase `MainApp` en el nivel de clase.  El método `GetAttribute` utiliza **GetCustomAttribute** para recuperar los valores almacenados en `DeveloperAttribute` en el nivel de clase antes de mostrarlos en la consola.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 Este programa muestra el texto siguiente cuando se ejecuta.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 Si no se encuentra el atributo, el método **GetCustomAttribute** inicializa `MyAttribute` en un valor nulo.  En este ejemplo se comprueba `MyAttribute` para una instancia de este tipo y se avisa al usuario si no se encuentra ningún atributo.  Si no se encuentra el atributo `DeveloperAttribute` en el ámbito de clases, se muestra el mensaje siguiente en la consola.  
  
```  
The attribute was not found.   
```  
  
 En este ejemplo se supone que la definición de atributo está en el espacio de nombres actual.  Recuerde que se ha de importar el espacio de nombres en que reside la definición de atributo si no está en el espacio de nombres actual.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## Recuperar varias instancias de un atributo aplicadas al mismo ámbito  
 En el ejemplo anterior, la clase que se desea inspeccionar y el atributo específico que se desea buscar se pasan como parámetros a <xref:System.Attribute.GetCustomAttribute%2A>.  Ese código funciona correctamente si se aplica una sola instancia de un atributo en el nivel de clase.  Sin embargo, si se aplican varias instancias de un atributo en el mismo nivel de clase, el método **GetCustomAttribute** no recupera toda la información.  En los casos en que se aplican varias instancias del mismo atributo al mismo ámbito se puede utilizar <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName> para colocar todas las instancias de un atributo en una matriz.  Por ejemplo, si dos instancias del atributo `DeveloperAttribute` se aplican en el nivel de clase de la misma clase, el método `GetAttribute` se puede modificar para que se muestre la información encontrada en ambos atributos.  Recuerde que, para aplicar varios atributos en el mismo nivel, el atributo se debe definir con la propiedad **AllowMultiple** establecida en **true** en el atributo <xref:System.AttributeUsageAttribute>.  
  
 El ejemplo de código siguiente muestra cómo se utiliza el método **GetCustomAttributes** para crear una matriz que hace referencia a todas las instancias de `DeveloperAttribute` en una clase dada.  Los valores de todos los atributos se muestran después en la consola.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 Si no se encuentran atributos, este código avisa al usuario.  En caso contrario, se muestra la información contenida en ambas instancias de `DeveloperAttribute`.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## Recuperar varias instancias de un atributo aplicadas a ámbitos diferentes  
 Los métodos <xref:System.Attribute.GetCustomAttributes%2A> y <xref:System.Attribute.GetCustomAttribute%2A> no buscan una clase completa y devuelven todas las instancias de un atributo de esa clase.  En su lugar, sólo buscan un miembro o un método especificado cada vez.  Si se tiene una clase con el mismo atributo aplicado a todos los miembros y se desea recuperar los valores de todos los atributos aplicados a dichos miembros, se debe proporcionar cada uno de los métodos o de los miembros individualmente a **GetCustomAttributes** y **GetCustomAttribute**.  
  
 En el ejemplo de código siguiente se toma una clase como parámetro y se busca el atributo `DeveloperAttribute` \(definido previamente\) en el nivel de clase y en todos los métodos individuales de esa clase.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 Si no se encuentran instancias del atributo `DeveloperAttribute` en el nivel de método o nivel de clase, el método `GetAttribute` notifica al usuario que no se han encontrado atributos y muestra el nombre del método o de la clase que no contiene el atributo.  Si se encuentra un atributo, los campos `Name`, `Level` y `Reviewed` se muestran en la consola.  
  
 Se pueden utilizar los miembros de la clase <xref:System.Type> para obtener los miembros y métodos individuales de la clase pasada como parámetro.  En este ejemplo se consulta primero el objeto **Type** para obtener información de atributos para el nivel de clase.  A continuación, utiliza <xref:System.Type.GetMethods%2A?displayProperty=fullName> para colocar las instancias de todos los métodos en una matriz de objetos <xref:System.Reflection.MemberInfo?displayProperty=fullName> para recuperar la información de atributos en el nivel del método.  También puede utilizar el método <xref:System.Type.GetProperties%2A?displayProperty=fullName> para comprobar los atributos en el nivel de propiedad o el método <xref:System.Type.GetConstructors%2A?displayProperty=fullName> para comprobar los atributos en el nivel de constructor.  
  
## Vea también  
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Atributos](../../../docs/standard/attributes/index.md)