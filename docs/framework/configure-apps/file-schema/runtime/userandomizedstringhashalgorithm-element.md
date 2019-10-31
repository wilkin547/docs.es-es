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
ms.openlocfilehash: cc9708b8cca6520932fbf0e1975a05cad5fad485
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115042"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<elemento > UseRandomizedStringHashAlgorithm
Determina si el Common Language Runtime calcula los códigos hash para las cadenas en cada dominio de aplicación.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<UseRandomizedStringHashAlgorithm >**  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si los códigos hash para las cadenas se calculan en función de cada dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|El Common Language Runtime no calcula los códigos hash para las cadenas en cada dominio de aplicación; se usa un solo algoritmo para calcular los códigos hash de la cadena. Este es el valor predeterminado.|  
|`1`|El Common Language Runtime calcula los códigos hash para las cadenas en cada dominio de aplicación. Las cadenas idénticas en dominios de aplicación diferentes y en procesos diferentes tendrán códigos hash diferentes.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, la clase <xref:System.StringComparer> y el método <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> utilizan un algoritmo hash único que genera un código hash coherente entre los dominios de aplicación. Esto es equivalente a establecer el atributo `enabled` del elemento `<UseRandomizedStringHashAlgorithm>` en `0`. Este es el algoritmo hash utilizado en el .NET Framework 4.  
  
 La clase <xref:System.StringComparer> y el método <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> también pueden usar un algoritmo hash diferente que calcula los códigos hash en cada dominio de aplicación. Como resultado, los códigos hash de las cadenas equivalentes serán diferentes en los dominios de aplicación. Se trata de una característica opcional; para aprovecharlo, debe establecer el atributo `enabled` del elemento `<UseRandomizedStringHashAlgorithm>` en `1`.  
  
 La búsqueda de cadena en una tabla hash es normalmente una operación O (1). Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una operación O (n<sup>2</sup>). Puede usar el elemento de configuración `<UseRandomizedStringHashAlgorithm>` para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de colisiones potenciales, especialmente cuando las claves desde las que se calculan los códigos hash se basan en la entrada de datos por pueden.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define una clase `DisplayString` que incluye una constante de cadena privada, `s`, cuyo valor es "This is a String". También incluye un método `ShowStringHashCode` que muestra el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se está ejecutando el método.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Al ejecutar el ejemplo sin proporcionar un archivo de configuración, se muestra un resultado similar al siguiente. Tenga en cuenta que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo, los códigos hash para la misma cadena se diferenciarán en el dominio de aplicación.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Cuando el archivo de configuración está presente, el ejemplo muestra el siguiente resultado:  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
