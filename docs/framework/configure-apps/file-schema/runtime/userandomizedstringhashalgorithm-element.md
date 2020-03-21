---
title: <UseRandomizedStringHashAlgorithm> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153782"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm> Element
Determina si Common Language Runtime calcula códigos hash para cadenas por dominio de aplicación.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si los códigos hash para cadenas se calculan por dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`0`|Common Language Runtime no calcula códigos hash para cadenas por dominio de aplicación; un solo algoritmo se utiliza para calcular códigos hash de cadena. Este es el valor predeterminado.|  
|`1`|Common Language Runtime calcula los códigos hash para las cadenas por dominio de aplicación. Cadenas idénticas en diferentes dominios de aplicación y en diferentes procesos tendrán diferentes códigos hash.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Observaciones  
 De forma <xref:System.StringComparer> predeterminada, <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> la clase y el método usan un único algoritmo hash que genera un código hash coherente entre los dominios de aplicación. Esto equivale a `enabled` establecer el `<UseRandomizedStringHashAlgorithm>` atributo `0`del elemento en . Este es el algoritmo hash utilizado en .NET Framework 4.  
  
 La <xref:System.StringComparer> clase <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> y el método también pueden usar un algoritmo hash diferente que calcula los códigos hash por dominio de aplicación. Como resultado, los códigos hash para cadenas equivalentes diferirán entre dominios de aplicación. Esta es una característica opt-in; para aprovecharlo, debe establecer `enabled` el atributo `<UseRandomizedStringHashAlgorithm>` del `1`elemento en .  
  
 La búsqueda de cadenas en una tabla hash suele ser una operación O(1). Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una operación O(n<sup>2</sup>). Puede utilizar `<UseRandomizedStringHashAlgorithm>` el elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de colisiones potenciales, especialmente cuando las claves a partir de las cuales se calculan los códigos hash se basan en la entrada de datos de los usuarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo `DisplayString` siguiente se define una `s`clase que incluye una constante de cadena privada, cuyo valor es "This is a string." También incluye un método `ShowStringHashCode` que presenta el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Cuando ejecute el ejemplo sin proporcionar un archivo de configuración, mostrará un resultado similar al siguiente. Observe que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Sin embargo, si agrega el archivo de configuración siguiente al directorio de ejemplo y, a continuación, ejecuta el ejemplo, los códigos hash para la misma cadena diferirán en función del dominio de aplicación.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
