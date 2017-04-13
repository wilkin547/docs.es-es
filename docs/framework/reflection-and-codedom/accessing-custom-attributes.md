---
title: "Accessing Custom Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "custom attributes, accessibility"
  - "attributes [.NET Framework], accessing"
  - "reflection, custom attributes"
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Accessing Custom Attributes
Tras asociar atributos a elementos del programa, se puede utilizar la reflexión para consultar su existencia y sus valores.  En las versiones 1.0 y 1.1 de .NET Framework, se examinan los atributos personalizados en el contexto de ejecución.  La versión 2.0 de .NET Framework proporciona un nuevo contexto de carga, el contexto de sólo reflexión, que se puede utilizar para examinar código que no puede cargarse para su ejecución.  
  
## Contexto de sólo reflexión  
 El código cargado en el contexto de sólo reflexión no se puede ejecutar.  Esto significa que no se pueden crear instancias de atributos personalizados, porque requeriría que se ejecutaran sus constructores.  Para cargar y examinar los atributos personalizados en el contexto de sólo reflexión, utilice la clase <xref:System.Reflection.CustomAttributeData>.  Puede obtener instancias de esta clase utilizando la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> estático.  Vea [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## Contexto de ejecución  
 Los principales métodos de reflexión para consultar atributos en el contexto de ejecución son <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> y <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>.  
  
 La accesibilidad de un atributo personalizado se comprueba con respecto al ensamblado donde se ha anexado.  Esto equivale a comprobar si un método en un tipo del ensamblado donde se ha asociado el atributo personalizado puede llamar al constructor de este último.  
  
 Los métodos como <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> comprueban la visibilidad y accesibilidad del argumento de tipo.  Sólo el código del ensamblado que contiene el tipo definido por el usuario puede recuperar un atributo personalizado de ese tipo utilizando **GetCustomAttributes**.  
  
 El ejemplo siguiente de C\# es un modelo de diseño típico de atributos personalizados.  En el ejemplo se muestra el modelo de reflexión de atributos personalizados en tiempo de ejecución.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 Si el motor en tiempo de ejecución intenta recuperar los atributos personalizados para el tipo de atributo personalizado público <xref:System.ComponentModel.DescriptionAttribute> asociado al método **GetLanguage**, realiza las siguientes acciones:  
  
1.  El motor en tiempo de ejecución comprueba que el argumento de tipo **DescriptionAttribute** de **Type.GetCustomAttributes**\(Type *tipo*\) es público y, por lo tanto, visible y accesible.  
  
2.  El motor en tiempo de ejecución comprueba que el tipo definido por el usuario **SRDescriptionAttribute** que se deriva de **DescriptionAttribute** es visible y accesible en el ensamblado **System.Web.DLL**, donde está asociada al método **GetLanguage**\(\).  
  
3.  El motor en tiempo de ejecución comprueba que el constructor de **SRDescriptionAttribute** es visible y accesible en el ensamblado **System.Web.DLL**.  
  
4.  El motor en tiempo de ejecución llama al constructor de **MyDescriptionAttribute** con los parámetros de atributo personalizados y devuelve el nuevo objeto al llamador.  
  
 El modelo de reflexión de atributos personalizados puede perder instancias de tipos definidos por el usuario fuera del ensamblado donde se define el tipo.  Esto no se diferencia de los miembros en la biblioteca del sistema en tiempo de ejecución que devuelven instancias de tipos definidos por el usuario, como [Type.GetMethods\(\)](frlrfSystemTypeClassGetMethodsTopic) que devuelve una matriz de objetos **RuntimeMethodInfo**.  Para evitar que un cliente detecte información sobre un tipo de atributo personalizado definido por el usuario, defina los miembros del tipo como no públicos.  
  
 En el ejemplo siguiente se muestra la forma básica de utilizar la reflexión para obtener acceso a los atributos personalizados.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## Vea también  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [Security Considerations for Reflection](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)