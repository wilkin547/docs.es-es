---
title: "&lt;UseRandomizedStringHashAlgorithm&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<UseRandomizedStringHashAlgorithm> (elemento)"
  - "UseRandomizedStringHashAlgorithm (elemento)"
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# &lt;UseRandomizedStringHashAlgorithm&gt; (elemento)
Determina si Common Language Runtime calcula los códigos hash para cadenas por cada dominio de aplicación.  
  
## Sintaxis  
  
```  
<UseRandomizedStringHashAlgorithm   
   enabled=0|1 />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si los códigos hash para las cadenas se calculan según el dominio de aplicación.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`0`|Common Language Runtime no calcula los códigos hash para cadenas según el dominio de aplicación; se usa un único algoritmo para calcular códigos hash de la cadena.  Éste es el valor predeterminado.|  
|`1`|Common Language Runtime calcula los códigos hash para cadenas por cada dominio de aplicación.  Las cadenas idénticas de distintos dominios de aplicación y distintos procesos tendrán distintos códigos hash.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## Comentarios  
 De forma predeterminada, la clase <xref:System.StringComparer> y el método <xref:System.String.GetHashCode%2A?displayProperty=fullName> utilizan un solo algoritmo hash que produce un código hash coherente entre dominios de aplicación.  Esto equivale al establecimiento del atributo `enabled` del elemento `<UseRandomizedStringHashAlgorithm>` en `0`.  Este es el algoritmo hash utilizado en [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 La clase <xref:System.StringComparer> y el método <xref:System.String.GetHashCode%2A?displayProperty=fullName> también pueden utilizar un algoritmo hash diferente que calcula códigos hash en cada dominio de aplicación.  Como resultado, los códigos hash para cadenas equivalentes variarán entre dominios de aplicación.  Esta es una característica opcional; para beneficiarse de ella, debe establecer el atributo `enabled` del elemento `<UseRandomizedStringHashAlgorithm>` en `1`.  
  
 La búsqueda de cadenas en una tabla hash suele ser una operación O \(1\).  Sin embargo, cuando un elevado número de colisiones aparece, la búsqueda puede convertirse en una operación O\(n<sup>2</sup>\).  Puede utilizar el elemento de configuración de `<UseRandomizedStringHashAlgorithm>` para generar un algoritmo hash aleatorio por dominio de aplicación, que a su vez limita el número de conflictos potenciales, especialmente cuando las teclas desde las que se calculan los códigos hash están basadas en entrada de datos por los usuarios.  
  
## Ejemplo  
 El ejemplo siguiente define una clase `DisplayString` que incluye una constante de cadena privada, `s`, cuyo valor es "Esto es una cadena". También incluye un método `ShowStringHashCode` que presenta el valor de cadena y su código hash junto con el nombre del dominio de aplicación en el que se ejecuta el método.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Cuando ejecute el ejemplo sin proporcionar un archivo de configuración, mostrará un resultado similar al siguiente.  Observe que los códigos hash de la cadena son idénticos en los dos dominios de aplicación.  
  
```  
  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
  
```  
  
 Sin embargo, si agrega el archivo de configuración siguiente al directorio de ejemplo y, a continuación, ejecuta el ejemplo, los códigos hash para la misma cadena diferirán en función del dominio de aplicación.  
  
```  
  
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
  
## Vea también  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.String.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>