---
title: "Uso del enlazador de serializaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab46c087-200c-45bf-9c95-5a6cda6e8b98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Uso del enlazador de serializaci&#243;n
Este ejemplo muestra cómo utilizar <xref:System.Runtime.Serialization.SerializationBinder> para cambiar la versión de un tipo genérico cuando se serializa.  
  
## Demostraciones  
 <xref:System.Runtime.Serialization.SerializationBinder>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
  
## Análisis  
 En este ejemplo se muestra cómo dos entidades que están destinadas a versiones diferentes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] pueden comunicar utilizando el formateador binario y el enlazador de serialización.  
  
 El desarrollo de este ejemplo se ha realizado con .NET Remoting.El ejemplo está compuesto de un servidor para [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], que implementa un contrato con tipos genéricos, y dos clientes diferentes, uno para [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] y otro para [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)].  
  
 El servidor asocia un objeto <xref:System.Runtime.Serialization.SerializationBinder> al formateador binario para poder cambiar la versión de los tipos de acuerdo con la serialización, de modo que ambos clientes puedan deserializar esos tipos correctamente.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Para ejecutar el cliente, haga clic con el botón secundario en la solución, SBGenericsVTS \(6 proyectos\) y, a continuación, seleccione **Propiedades**.  
  
2.  En **Propiedades comunes**, seleccione **Proyecto de inicio** y, a continuación, haga clic en **Proyectos de inicio múltiples**.  
  
3.  Seleccione **Servidor** primero, a continuación **Client20** y, después, **Client40**.Seleccione la acción **Iniciar** para estos tres proyectos y deje el resto establecido en **Ninguno**.  
  
4.  Haga clic en **Aceptar** y, a continuación, presione F5 para ejecutar el ejemplo.