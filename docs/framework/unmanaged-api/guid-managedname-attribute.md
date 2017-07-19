---
title: "GUID_ManagedName (Atributo) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "GUID_ManagedName"
apilocation: 
  - "alink.dll"
apitype: "COM"
f1_keywords: 
  - "GUID_ManagedName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID_ManagedName (atributo)"
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# GUID_ManagedName (Atributo)
Define un atributo de interfaz personalizado que especifica el nombre de espacio de nombres administrado para una biblioteca de \(componentes COM\) del modelo de objetos de componente.  
  
## Sintaxis  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### Parámetros  
 `value`  
 El nombre de espacio de nombres administrado para la biblioteca.  
  
## Definición  
 `GUID_ManagedName` se define en Cor.h como sigue:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## Comentarios  
 Un atributo de interfaz personalizado define los metadatos de un objeto en la biblioteca de tipos.  
  
 Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=fullName> o <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=fullName> para recuperar el nombre administrado del atributo.  
  
 Para obtener más información, vea [Interface Attributes](../Topic/Interface%20Attributes.md) documentación de referencia de Visual C\+\+.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una definición de biblioteca mediante el `GUID_ManagedName` atributo.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## Requisitos  
 **Encabezado:** Cor.h