---
title: "Constrained Execution Regions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "constrained execution regions"
  - "CERs"
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Constrained Execution Regions
Un área de ejecución restringida \(CER\) forma parte de un mecanismo para crear código administrado confiable.  Una CER define un área en la que Common Language Runtime \(CLR\) tiene restringida la producción de excepciones fuera de banda que impedirían que el código contenido en el área se ejecutara por completo.  Dentro de esa área, el código de usuario tiene restringida la ejecución del código que provocaría la producción de excepciones fuera de banda.  El método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> debe ir colocado inmediatamente antes un bloque `try` y marca los bloques `catch`, `finally` y `fault` como áreas de ejecución restringida.  Una vez marcado como área restringida, el código sólo debe llamar a otro código con contratos de alta confiabilidad y el código no debería asignar ni realizar llamadas virtuales a métodos sin preparar o no confiables a menos que el código esté preparado para controlar errores.  La CLR retrasa las anulaciones del subproceso para el código que se está ejecutando en una CER.  
  
 Las áreas de ejecución restringida se utilizan de diferentes formas en la CLR además de un bloque `try` anotado, principalmente los finalizadores críticos que se están ejecutando en clases derivadas de la clase <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> y el código ejecutado usando el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>.  
  
## Preparación adelantada de las CER  
 Common Language Runtime prepara de antemano las CER para evitar condiciones de falta de memoria.  La preparación adelantada es necesaria para que Common Language Runtime no cause una condición de falta de memoria durante la compilación Just\-In\-Time o la carga de tipos.  
  
 El desarrollador debe indicar que un área de código es una CER:  
  
-   De antemano se preparan el área CER de nivel superior y los métodos de todo el gráfico de llamadas que tienen aplicado el atributo <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>.  <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> sólo puede especificar garantías de <xref:System.Runtime.ConstrainedExecution.Cer> o <xref:System.Runtime.ConstrainedExecution.Cer>.  
  
-   La preparación adelantada no se puede realizar para llamadas que no se pueden determinar estadísticamente, como un envío virtual.  Utilice el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> en estos casos.  Al utilizar el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>, se debería aplicar el atributo <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> al código limpio.  
  
## Restricciones  
 Los usuarios tienen restricciones en cuanto al tipo de código que pueden escribir en una CER.  El código no puede producir una excepción fuera de banda, como podría ser el resultado de las operaciones siguientes:  
  
-   Asignación explícita.  
  
-   Conversiones boxing.  
  
-   Adquirir un bloqueo.  
  
-   Llamar virtualmente a métodos no preparados.  
  
-   Llamar a métodos con un contrato de confiabilidad débil o inexistente.  
  
 En la versión 2.0 de .NET Framework, estas restricciones son instrucciones.  Los diagnósticos se proporcionan mediante herramientas de análisis de código.  
  
## Contratos de confiabilidad  
 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> es un atributo personalizado que documenta las garantías de confiabilidad y el estado de daños de un método determinado.  
  
### Garantías de confiabilidad  
 Las garantías de confiabilidad, representadas por valores de enumeración <xref:System.Runtime.ConstrainedExecution.Cer>, indican el grado de confiabilidad de un método determinado:  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  En condiciones excepcionales, se podría producir un error en el método.  En este caso, el método devuelve información al método de llamada sobre si se realizó correctamente o no.  El método debe estar contenido en una CER para garantizar que puede informar del valor devuelto.  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  El método, tipo o ensamblado no tienen conocimiento de lo que es una CER y es muy probable que no sea seguro llamarlo desde dentro de una CER sin una mitigación significativa del estado dañado.  No aprovecha las garantías de las áreas CER.  Esto implica lo siguiente:  
  
    1.  En condiciones excepcionales, se podría producir un error en el método.  
  
    2.  El método podría o no informar de que se produjo un error.  
  
    3.  El método no está escrito para utilizar un área CER, el escenario más probable.  
  
    4.  Si un método, tipo, o el ensamblado no está identificado explícitamente como de resultado correcto, se identifica implícitamente como <xref:System.Runtime.ConstrainedExecution.Cer>.  
  
-   <xref:System.Runtime.ConstrainedExecution.Cer>.  En condiciones excepcionales, el método tiene garantía de finalizar correctamente.  Para conseguir este nivel de confiabilidad, siempre debería construir un área CER alrededor del método llamado, incluso cuando se lo llame desde un área que no sea CER.  Un método finaliza correctamente si consigue lo que se esperaba del mismo, aunque la corrección puede ser subjetiva.  Por ejemplo, marcar el contador Count con `ReliabilityContractAttribute(Cer.Success)` implica que, cuando se ejecuta dentro de un área CER, siempre devuelve un recuento del número de elementos incluidos en la <xref:System.Collections.ArrayList> y que nunca puede dejar los campos internos en estado indeterminado.  Sin embargo, el método <xref:System.Threading.Interlocked.CompareExchange%2A> está marcado también como correcto, con la comprensión de que el estado de correcto podría significar que el valor no se pudo reemplazar con un nuevo valor a causa de una condición de carrera.  El punto principal es que el comportamiento del método es como el que está documentado y no es necesario escribir código de CER para que espere ningún comportamiento inusual aparte del que podría tener el código correcto pero no confiable.  
  
### Niveles de daños  
 Los niveles de daño, representados por valores de enumeración <xref:System.Runtime.ConstrainedExecution.Consistency>, indican hasta qué nivel podría estar dañado en un entorno determinado:  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  En condiciones excepcionales, Common Language Runtime \(CLR\) no proporciona ninguna garantía relativa a la coherencia del estado en el dominio de aplicación actual.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  En condiciones excepcionales, el método tiene garantía de un daño de estado limitado a la instancia actual.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>, en condiciones excepcionales, CLR no supone ninguna garantía relativa a la coherencia del estado; es decir, la condición podría dañar el proceso.  
  
-   <xref:System.Runtime.ConstrainedExecution.Consistency>.  Bajo condiciones excepcionales, hay garantía de que el método no daña el estado.  
  
## Confiabilidad de try\/catch\/finally  
 `try/catch/finally` es un mecanismo del control de excepciones con el mismo nivel de garantías de previsibilidad que el de las versiones no administradas.  El bloque `catch/finally` es el área CER.  Los métodos incluidos en el bloque requieren la preparación de antemano y deben ser no interrumpibles.  
  
 En la versión 2.0 de .NET Framework, el código informa al motor en tiempo de ejecución de que una instrucción try es confiable llamando a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> inmediatamente anterior a un bloque try.  <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> es miembro de <xref:System.Runtime.CompilerServices.RuntimeHelpers>, una clase de soporte de compilador.  Llame a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> directamente dependiendo de su disponibilidad mediante compiladores.  
  
## Áreas no interrumpibles  
 Un área no interrumpible agrupa un conjunto de instrucciones en una CER.  
  
 En la versión 2.0 de .NET Framework, con dependencia de la disponibilidad mediante compatibilidad del compilador, el código de usuario crea áreas ininterrumpibles con una estructura try\/catch\/finally confiable que contiene un bloque try\/catch vacío precedido de una llamada de método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.  
  
## Objeto finalizador crítico  
 Un objeto <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> garantiza que la recolección de elementos no utilizados ejecutará el finalizador.  Tras la asignación, se preparan de antemano el finalizador y su gráfico de llamadas.  El método finalizador se ejecuta en una CER y debe obedecer todas las restricciones de las CER y los finalizadores.  
  
 Los tipos que heredan de <xref:System.Runtime.InteropServices.SafeHandle> y <xref:System.Runtime.InteropServices.CriticalHandle> tienen la garantía de que su finalizador se ejecuta dentro de una CER.  Implemente <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> en clases derivadas <xref:System.Runtime.InteropServices.SafeHandle> para ejecutar cualquier código necesario para liberar el identificador.  
  
## Código no permitido en las CER  
 Dentro de las CER no están permitidas las operaciones siguientes:  
  
-   Asignaciones explícitas.  
  
-   Adquirir un bloqueo.  
  
-   Conversiones boxing.  
  
-   Acceso a matriz multidimensional.  
  
-   Llamadas métodos a través de reflexión.  
  
-   <xref:System.Threading.Monitor.Enter%2A> o <xref:System.IO.FileStream.Lock%2A>.  
  
-   Comprobaciones de seguridad.  No se realizan peticiones, sólo peticiones de vínculo.  
  
-   <xref:System.Reflection.Emit.OpCodes.Isinst> y <xref:System.Reflection.Emit.OpCodes.Castclass> para los objetos COM y servidores proxy.  
  
-   Obtener o establecer campos de un servidor proxy transparente.  
  
-   Serialización.  
  
-   Punteros de función y delegados.  
  
## Vea también  
 [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md)