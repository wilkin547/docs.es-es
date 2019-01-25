---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bb4286ea6055d2df9111b2222b137f2668bfdfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681045"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a>&lt;UseRandomizedStringHashAlgorithm&gt; elemento
Determina si common language runtime calcula los códigos hash para cadenas en una por cada dominio de aplicación.  
  
 \<configuration>  
\<runtime>  
\<UseRandomizedStringHashAlgorithm>  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si se calculan los códigos hash para cadenas en una por cada dominio de aplicación.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|Common language runtime no calcula los códigos hash para cadenas en una por cada dominio de aplicación; se usa un solo algoritmo para calcular los códigos hash de cadena. Este es el valor predeterminado.|  
|`1`|Common language runtime calcula los códigos hash para cadenas en una por cada dominio de aplicación. Las cadenas idénticas en distintos dominios de aplicación y en distintos procesos tendrán distintos códigos hash.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, el <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método usa un solo algoritmo hash que genera un código hash coherente entre dominios de aplicación. Esto es equivalente a establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `0`. Este es el algoritmo hash utilizado en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 El <xref:System.StringComparer> clase y el <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> método también puede usar un algoritmo hash diferente que calcula códigos hash en una por cada dominio de aplicación. Como resultado, los códigos hash para cadenas equivalentes variarán entre dominios de aplicación. Se trata de una característica opcional; para aprovechar las ventajas de la misma, debe establecer el `enabled` atributo de la `<UseRandomizedStringHashAlgorithm>` elemento `1`.  
  
 La búsqueda de cadenas en una tabla hash suele ser una operación o (1). Sin embargo, cuando se produce un gran número de colisiones, la búsqueda puede convertirse en una O (n<sup>2</sup>) operación. Puede usar el `<UseRandomizedStringHashAlgorithm>` elemento de configuración para generar un algoritmo hash aleatorio por dominio de aplicación, lo que a su vez limita el número de conflictos potenciales, especialmente cuando las claves desde el que se calculan los códigos hash se basan en la entrada de datos los usuarios.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `DisplayString` clase que incluya una constante de cadena privada, `s`, cuyo valor es "Es una cadena". También incluye un `ShowStringHashCode` método que muestra el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Al ejecutar el ejemplo sin proporcionar un archivo de configuración, muestra un resultado similar al siguiente. Tenga en cuenta que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Sin embargo, si agrega el siguiente archivo de configuración al directorio del ejemplo y, a continuación, ejecute el ejemplo, los códigos hash para la misma cadena diferirán por dominio de aplicación.  
  
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
