---
title: regiones de ejecución restringidas
description: Introducción a las regiones de ejecución restringidas (CER), que forman parte de un mecanismo para la creación de código administrado confiable.
ms.date: 03/30/2017
helpviewer_keywords:
- constrained execution regions
- CERs
ms.assetid: 99354547-39c1-4b0b-8553-938e8f8d1808
ms.openlocfilehash: 5014885e186b1fff16543c09d5652958f2463e3d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266862"
---
# <a name="constrained-execution-regions"></a>regiones de ejecución restringidas

Una región de ejecución restringida (CER) es parte de un mecanismo para crear código administrado de confianza. Una CER define un área en la que Common Language Runtime (CLR) no puede producir excepciones fuera de banda que eviten que el código del área se ejecute en su totalidad. Dentro de esa región, el código de usuario no puede ejecutar código que pueda producir excepciones fuera de banda. El método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> debe ir inmediatamente antes del bloque `try` y marca los bloques `catch`, `finally` y `fault` como regiones de ejecución restringidas. Una vez marcada como región restringida, el código solo debe llamar a otro código con contratos de fiabilidad estables y no debe asignar ni realizar llamadas virtuales a métodos no preparados o no confiables a menos que esté preparado para controlar errores. CLR retrasa las anulaciones de subprocesos del código que se está ejecutando en una CER.  

> [!IMPORTANT]
> CER solo se admite en .NET Framework. Este artículo no se aplica a .NET Core o .NET 5 y versiones posteriores.

 Las regiones de ejecución restringidas se usan de diferentes formas en CLR además de en un bloque anotado `try`, en concreto, finalizadores críticos que se ejecutan en clases derivadas de la clase <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> y código ejecutado mediante el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>.  
  
## <a name="cer-advance-preparation"></a>Preparación anticipada de CER  

 CLR prepara las CER de antemano para evitar situaciones de memoria insuficiente. La preparación anticipada es necesaria para que CLR no provoque una situación de memoria insuficiente durante la compilación Just-In-Time o la carga de tipos.  
  
 Es necesario que el desarrollador indique que una región de código es una CER:  
  
- La región CER de nivel superior y los métodos del gráfico de llamadas completo que tienen el atributo <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> aplicado se preparan de antemano. <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> solo puede declarar garantías de <xref:System.Runtime.ConstrainedExecution.Cer.Success> o <xref:System.Runtime.ConstrainedExecution.Cer.MayFail>.  
  
- No es posible realizar la preparación anticipada de las llamadas que no se pueden determinar de forma estática, como la distribución virtual. En estos casos use el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>. Cuando se usa el método <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>, se debe aplicar el atributo <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute> al código de limpieza.  
  
## <a name="constraints"></a>Restricciones  

 Los usuarios están limitados con respecto al tipo de código que pueden escribir en una CER. El código no puede producir una excepción fuera de banda, como la que podrían ocasionar las siguientes operaciones:  
  
- Asignación explícita.  
  
- Conversión boxing.  
  
- Adquisición de un bloqueo.  
  
- Llamada a métodos no preparados de forma virtual.  
  
- Llamada a métodos con un contrato de fiabilidad débil o inexistente.  
  
 En la versión 2.0 de .NET Framework, estas restricciones son directrices. Los diagnósticos se proporcionan a través de herramientas de análisis de código.  
  
## <a name="reliability-contracts"></a>Contratos de fiabilidad  

 <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> es un atributo personalizado que documenta las garantías de fiabilidad y el estado de daños de un método determinado.  
  
### <a name="reliability-guarantees"></a>Garantías de fiabilidad  

 Las garantías de fiabilidad, representadas por valores de enumeración <xref:System.Runtime.ConstrainedExecution.Cer>, indican el grado de fiabilidad de un método determinado:  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.MayFail>. En condiciones excepcionales, se puede producir un error en el método. En este caso, el método informa al método de la llamada de si esta se ha realizado correctamente o no. El método debe estar incluido en una CER para garantizar que puede notificar el valor devuelto.  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.None>. El método, tipo o ensamblado no tiene ningún concepto de una CER y lo más probable es que no sea seguro llamar desde dentro de una CER sin mitigación significativa de daños de estado. No se aprovecha de las garantías de la CER. Esto implica lo siguiente:  
  
    1. En condiciones excepcionales, se puede producir un error en el método.  
  
    2. El método podría o no informar de que se ha producido un error.  
  
    3. El método no se escribe para usar una CER, el escenario más probable.  
  
    4. Si un método, tipo o ensamblado no se identifica explícitamente como correcto, se identifica implícitamente como <xref:System.Runtime.ConstrainedExecution.Cer.None>.  
  
- <xref:System.Runtime.ConstrainedExecution.Cer.Success>. En condiciones excepcionales, se garantiza que el método será correcto. Para lograr este nivel de fiabilidad, siempre debería crear una CER alrededor del método al que se llama, incluso cuando se llama desde dentro de una región no CER. Un método es correcto si logra lo que pretendía, aunque la corrección se puede ver de forma subjetiva. Por ejemplo, marcar Count con `ReliabilityContractAttribute(Cer.Success)` implica que cuando se ejecuta en una CER, siempre devuelve un recuento del número de elementos de <xref:System.Collections.ArrayList> y que nunca puede dejar los campos internos en un estado indeterminado.  Pero el método <xref:System.Threading.Interlocked.CompareExchange%2A> también está marcado como correcto, con la asunción de que correcto puede significar que el valor no se ha podido reemplazar por un nuevo valor a causa de una condición de carrera.  El punto clave es que el método se comporta de la manera en que se ha documentado que lo hará y no es necesario escribir código de la CER para esperar ningún comportamiento inusual más allá del aspecto que tendría un código correcto pero no confiable.  
  
### <a name="corruption-levels"></a>Niveles de daños  

 Los niveles de daños, representados por valores de enumeración <xref:System.Runtime.ConstrainedExecution.Consistency>, indican cuánto podría estar dañado en un entorno determinado:  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>. En condiciones excepcionales, Common Language Runtime (CLR) no ofrece ninguna garantía con respecto a la coherencia del estado en el dominio de aplicación actual.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance>. En condiciones excepcionales, se garantiza que el método limita los daños de estado a la instancia actual.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>. En condiciones excepcionales, CLR no ofrece ninguna garantía con respecto a la coherencia del estado; es decir, la condición podría dañar el proceso.  
  
- <xref:System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState>. En condiciones excepcionales, se garantiza que el método no dañe el estado.  
  
## <a name="reliability-trycatchfinally"></a>try/catch/finally de fiabilidad  

 `try/catch/finally` de fiabilidad es un mecanismo de control de excepciones con el mismo nivel de garantías de previsibilidad que la versión no administrada. El bloque `catch/finally` es la CER. Los métodos del bloque necesitan preparación anticipada y deben ser no interrumpibles.  
  
 En la versión 2.0 de .NET Framework, el código informa al tiempo de ejecución de que un elemento try es de confianza mediante una llamada al elemento <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> inmediatamente anterior a un bloque try. <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> es miembro de <xref:System.Runtime.CompilerServices.RuntimeHelpers>, una clase de soporte del compilador. Llame a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> directamente pendiente de disponibilidad mediante compiladores.  
  
## <a name="noninterruptible-regions"></a>Regiones no interrumpibles  

 Una región no interrumpible agrupa un conjunto de instrucciones en una CER.  
  
 En .NET Framework versión 2.0, pendiente de disponibilidad mediante compatibilidad del compilador, el código de usuario crea regiones no interrumpibles con un elemento try/catch/finally de confianza que contiene un bloque try/catch vacío precedido por una llamada al método <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.  
  
## <a name="critical-finalizer-object"></a>Critical Finalizer Object  

 Un elemento <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject> garantiza que la recolección de elementos no utilizados va a ejecutar el finalizador. Tras la asignación, el finalizador y su gráfico de llamadas se preparan de antemano. El método finalizador se ejecuta en una CER y debe obedecer todas las restricciones de las CER y los finalizadores.  
  
 Se garantiza que el finalizador de todos los tipos que heredan de <xref:System.Runtime.InteropServices.SafeHandle> y <xref:System.Runtime.InteropServices.CriticalHandle> se ejecuta dentro de una CER. Implemente <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> en clases derivadas <xref:System.Runtime.InteropServices.SafeHandle> para ejecutar cualquier código necesario para liberar el controlador.  
  
## <a name="code-not-permitted-in-cers"></a>Código no permitido en las CER  

 En las CER no se permiten las operaciones siguientes:  
  
- Asignaciones explícitas.  
  
- Adquisición de un bloqueo.  
  
- Conversión boxing.  
  
- Acceso a una matriz multidimensional.  
  
- Llamadas a métodos mediante reflexión.  
  
- <xref:System.Threading.Monitor.Enter%2A> o <xref:System.IO.FileStream.Lock%2A>.  
  
- Comprobaciones de seguridad. No se realizan peticiones, solo peticiones de vínculos.  
  
- <xref:System.Reflection.Emit.OpCodes.Isinst> y <xref:System.Reflection.Emit.OpCodes.Castclass> para objetos COM y servidores proxy  
  
- Obtención o establecimiento de campos en un servidor proxy transparente.  
  
- Serialización.  
  
- Punteros de función y delegados.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos recomendados para la confiabilidad](reliability-best-practices.md)
