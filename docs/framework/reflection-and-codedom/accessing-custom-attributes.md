---
title: Acceso a atributos personalizados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
ms.openlocfilehash: a5651e9dc8cf40e737dd523ec5d29e876a9c0765
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130297"
---
# <a name="accessing-custom-attributes"></a>Acceso a atributos personalizados
Después de asociar atributos a elementos de un programa, puede usar la reflexión para consultar su existencia y sus valores. En .NET Framework versión 1.0 y 1.1, los atributos personalizados se examinan en el contexto de ejecución. .NET Framework versión 2.0 proporciona un nuevo contexto de carga, el contexto de solo reflexión, que puede usarse para examinar el código que no se puede cargar para su ejecución.  
  
## <a name="the-reflection-only-context"></a>Contexto de solo reflexión  
 El código cargado en el contexto de solo reflexión no se puede ejecutar. Esto significa que no se pueden crear instancias de atributos personalizados, porque requeriría la ejecución de sus constructores. Para cargar y examinar los atributos personalizados en el contexto de solo reflexión, use la clase <xref:System.Reflection.CustomAttributeData>. Puede obtener instancias de esta clase mediante la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> estático. Vea [Cómo: Cargar ensamblados en el contexto de solo reflexión](how-to-load-assemblies-into-the-reflection-only-context.md).  
  
## <a name="the-execution-context"></a>Contexto de ejecución  
 Los principales métodos de reflexión para consultar los atributos en el contexto de ejecución son <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> y <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.  
  
 La accesibilidad de un atributo personalizado se comprueba con respecto al ensamblado al que está asociado. Esto equivale a comprobar si un método en un tipo del ensamblado al que está asociado el atributo personalizado puede llamar al constructor del atributo personalizado.  
  
 Los métodos como <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> comprueban la visibilidad y la accesibilidad del argumento de tipo. Solo el código del ensamblado que contiene el tipo definido por el usuario puede recuperar un atributo personalizado de ese tipo mediante **GetCustomAttributes**.  
  
 El siguiente ejemplo de C# es un modelo de diseño típico de atributos personalizados en el que se muestra el modelo de reflexión de atributos personalizados en tiempo de ejecución.  
  
```csharp
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
  
 Si el tiempo de ejecución intenta recuperar los atributos personalizados para el tipo de atributo personalizado público <xref:System.ComponentModel.DescriptionAttribute> asociado al método **GetLanguage**, realiza las acciones siguientes:  
  
1. El tiempo de ejecución comprueba que el argumento de tipo **DescriptionAttribute** de **Type.GetCustomAttributes**(Type *type*) es público y, por tanto, es visible y accesible.  
  
2. El tiempo de ejecución comprueba que el tipo definido por el usuario **MyDescriptionAttribute** que se deriva de **DescriptionAttribute** es visible y accesible en el ensamblado **System.Web.DLL**, donde está asociado al método **GetLanguage**().  
  
3. El tiempo de ejecución comprueba que el constructor de **MyDescriptionAttribute** es visible y accesible dentro del ensamblado **System.Web.DLL**.  
  
4. El tiempo de ejecución llama al constructor de **MyDescriptionAttribute** con los parámetros de atributo personalizados y devuelve el nuevo objeto al llamador.  
  
 En el modelo de reflexión de atributos personalizados, pueden producirse pérdidas de instancias de tipos definidos por el usuario fuera del ensamblado donde está definido el tipo. Esto no es diferente de los miembros de la biblioteca del sistema en tiempo de ejecución que devuelven instancias de tipos definidos por el usuario, como cuando <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> devuelve una matriz de objetos **RuntimeMethodInfo**. Para evitar que a un cliente detecte información sobre un tipo de atributo personalizado definido por el usuario, defina los miembros del tipo como no públicos.  
  
 En el ejemplo siguiente se muestra la forma básica de usar la reflexión para obtener acceso a atributos personalizados.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [Ver información tipos](viewing-type-information.md)
- [Consideraciones de seguridad sobre la reflexión](security-considerations-for-reflection.md)
