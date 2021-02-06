---
description: 'Más información acerca de: <UseRandomizedStringHashAlgorithm> elemento'
title: <UseRandomizedStringHashAlgorithm> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: bb651fc9c9f6f3df448ed5ce19e81c1ae092838c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639983"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm> (Elemento)

Determina si el Common Language Runtime calcula los códigos hash para las cadenas en cada dominio de aplicación.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si los códigos hash para las cadenas se calculan en función de cada dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
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
  
## <a name="remarks"></a>Observaciones  

 De forma predeterminada, la <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método usan un algoritmo hash único que genera un código hash coherente entre los dominios de aplicación. Esto es equivalente a establecer el `enabled` atributo del `<UseRandomizedStringHashAlgorithm>` elemento en `0` . Este es el algoritmo hash utilizado en el .NET Framework 4.  
  
 La <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método también pueden usar un algoritmo hash diferente que calcula los códigos hash en cada dominio de aplicación. Como resultado, los códigos hash de las cadenas equivalentes serán diferentes en los dominios de aplicación. Se trata de una característica opcional; para aprovecharlo, debe establecer el `enabled` atributo del `<UseRandomizedStringHashAlgorithm>` elemento en `1` .  
  
 La búsqueda de cadena en una tabla hash es normalmente una operación O (1). Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una operación O (n<sup>2</sup>). Puede usar el `<UseRandomizedStringHashAlgorithm>` elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de colisiones potenciales, especialmente cuando las claves de las que se calculan los códigos hash se basan en la entrada de datos por parte de los usuarios.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se define una `DisplayString` clase que incluye una constante de cadena privada, `s` , cuyo valor es "This is a String". También incluye un método `ShowStringHashCode` que presenta el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
