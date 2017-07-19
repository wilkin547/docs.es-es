---
title: "SpinWait | Microsoft Docs"
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
  - "synchronization primitives, SpinWait"
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# SpinWait
<xref:System.Threading.SpinWait?displayProperty=fullName> es un tipo de sincronización ligero que se puede utilizar en escenarios de bajo nivel para evitar los costosos cambios de contexto y las transiciones del kernel que se requieren para los eventos de kernel.  En los equipos de varios núcleos, cuando no se espera que un recurso sea retenido durante períodos de tiempo prolongados, puede ser más eficaz que un subproceso en espera gire en modo usuario durante unas docenas o centenares de ciclos y, a continuación, vuelva a intentar adquirir el recurso.  Si el recurso está disponible después de girar, habremos ahorrado varios miles de ciclos.  Si el recurso todavía no está disponible, solamente habremos gastado unos cuantos ciclos e igualmente podemos entrar en una espera basada en kernel.  Esta combinación de giro y espera se denomina en ocasiones *operación de espera de dos fases*.  
  
 <xref:System.Threading.SpinWait> se ha diseñado para utilizarlo en combinación con los tipos de .NET Framework que contienen eventos de kernel, como <xref:System.Threading.ManualResetEvent>.  <xref:System.Threading.SpinWait> también se puede utilizar por sí solo para la funcionalidad del giro básica en un único programa.  
  
 <xref:System.Threading.SpinWait> es más que un bucle vacío sin más.  Se ha implementado con todo cuidado para proporcionar un comportamiento de giro correcto para el caso general e iniciará por sí mismo cambios de contexto si gira durante el tiempo suficiente \(aproximadamente, el tiempo necesario para una transición del kernel\).  Por ejemplo, en los equipos de un núcleo, <xref:System.Threading.SpinWait> cede de inmediato el intervalo de tiempo del subproceso, porque al girar se bloquea el progreso de avance en todos los subprocesos.  <xref:System.Threading.SpinWait> también cede el paso incluso en equipos de varios núcleos, para evitar que el subproceso en espera bloquee otros subprocesos de más prioridad o el recolector de elementos no utilizados.  Por consiguiente, si utiliza <xref:System.Threading.SpinWait> en una operación de espera de dos fases, recomendamos que invoque la espera del kernel antes de que <xref:System.Threading.SpinWait> inicie un cambio de contexto.  <xref:System.Threading.SpinWait> proporciona la propiedad <xref:System.Threading.SpinWait.NextSpinWillYield%2A>, que puede comprobar antes de cada llamada a <xref:System.Threading.SpinWait.SpinOnce%2A>.  Cuando la propiedad devuelve `true`, inicie su propia operación de espera.  Para obtener un ejemplo, vea [How to: Use SpinWait to Implement a Two\-Phase Wait Operation](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Si no está realizando una operación de espera de dos fases, sino que se limita a girar hasta que se cumpla alguna condición, puede permitir que <xref:System.Threading.SpinWait> realice sus cambios de contexto para que se comporte correctamente en el entorno del sistema operativo Windows.  El siguiente ejemplo básico muestra un objeto <xref:System.Threading.SpinWait> en una pila sin bloqueo.  Si necesita una pila segura para subprocesos de alto rendimiento, considere la posibilidad de usar <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## Vea también  
 <xref:System.Threading.Thread.SpinWait%2A>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)