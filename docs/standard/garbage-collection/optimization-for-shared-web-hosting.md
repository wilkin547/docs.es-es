---
title: "Optimization for Shared Web Hosting | Microsoft Docs"
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
  - "garbage collection, Web hosting"
  - "garbage collection, optimizing"
  - "garbage collection, shared Web hosting"
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Optimization for Shared Web Hosting
Si es el administrador de un servidor compartido que hospeda varios sitios web pequeños, puede optimizar el rendimiento y aumentar capacidad de los sitios agregando el siguiente valor `gcTrimCommitOnLowMemory` al nodo `runtime` en el archivo Aspnet.config del directorio .NET Framework:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  Este valor sólo se recomienda en casos de hospedaje web compartido.  
  
 Debido a que el recolector de elementos no utilizados conserva la memoria para futuras asignaciones, el espacio confirmado puede ser mayor que el estrictamente necesario.  Puede reducir este espacio para ajustar los tiempos cuando la memoria del sistema está muy cargada.  La reducción de este espacio confirmado mejora el rendimiento y amplía la capacidad para hospedar más sitios.  
  
 Cuando se habilita el valor `gcTrimCommitOnLowMemory`, el recolector de elementos no utilizados evalúa la carga de la memoria del sistema y activa un modo de reducción cuando la carga alcanza el 90%.  El modo de reducción se mantiene hasta que la carga desciende por debajo del 85%.  
  
 Cuando las condiciones lo permiten, el recolector de elementos no utilizados puede decidir que el valor `gcTrimCommitOnLowMemory` no es útil para la aplicación actual y lo pasa por alto.  
  
## Ejemplo  
 El siguiente fragmento de XML muestra cómo habilitar el valor `gcTrimCommitOnLowMemory`.  Los puntos suspensivos indican otros valores que podrían estar en el nodo `runtime`.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## Vea también  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)