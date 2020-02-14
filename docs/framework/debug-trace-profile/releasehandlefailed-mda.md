---
title: MDA de releaseHandleFailed
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), handles
- release handle failed
- CriticalHandle class, run-time errors
- releaseHandleFailed MDA
- ReleaseHandle method
- SafeHandle class, run-time errors
- MDAs (managed debugging assistants), handles
ms.assetid: 44cd98ba-95e5-40a1-874d-e8e163612c51
ms.openlocfilehash: 265344cb100a41cde5443cd0914dc66271aabf93
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216128"
---
# <a name="releasehandlefailed-mda"></a>MDA de releaseHandleFailed
El Asistente para depuración administrada (MDA) de `releaseHandleFailed` se activa para notificar a los desarrolladores cuando el método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> de una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> o <xref:System.Runtime.InteropServices.CriticalHandle> devuelve `false`.  
  
## <a name="symptoms"></a>Síntomas  
 Pérdidas de recursos o de memoria.  Si se produce un error en el método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> de la clase que deriva de <xref:System.Runtime.InteropServices.SafeHandle> o <xref:System.Runtime.InteropServices.CriticalHandle>, es posible que el recurso encapsulado por la clase no se haya liberado o limpiado.  
  
## <a name="cause"></a>Causa  
 Los usuarios deben proporcionar la implementación del método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> si crean clases que deriven de <xref:System.Runtime.InteropServices.SafeHandle> o <xref:System.Runtime.InteropServices.CriticalHandle>. Por lo tanto, las circunstancias son específicas de cada recurso. Sin embargo, los requisitos son los siguientes:  
  
- Los tipos <xref:System.Runtime.InteropServices.SafeHandle> y <xref:System.Runtime.InteropServices.CriticalHandle> representan contenedores que contienen recursos de procesos fundamentales. Si se produce una pérdida de memoria, con el tiempo, esto puede inutilizar el proceso.  
  
- Para que el método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> realice su función, no debe haber errores en él. Una vez que el proceso adquiere este tipo de recurso, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> es la única manera de liberarlo. Por lo tanto, los errores conllevan pérdidas de recursos.  
  
- Todos los errores que se producen durante la ejecución de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> y que impiden que se libere el recurso, son errores en la implementación del propio método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>. Es responsabilidad del programador asegurarse de que se cumpla el contrato, aunque ese código, para realizar su función, llame a un código creado por otra persona.  
  
## <a name="resolution"></a>Solución  
 El código que utiliza el tipo específico <xref:System.Runtime.InteropServices.SafeHandle> (o <xref:System.Runtime.InteropServices.CriticalHandle>) que generó la notificación del MDA se debe revisar, para buscar los lugares donde se extrae el valor de identificador sin formato de <xref:System.Runtime.InteropServices.SafeHandle> y se copia a otro lugar. Esta es la causa habitual de errores dentro de las implementaciones de <xref:System.Runtime.InteropServices.SafeHandle> o <xref:System.Runtime.InteropServices.CriticalHandle>, porque el tiempo de ejecución deja de realizar un seguimiento del uso del valor de identificador sin formato. Si más tarde se cierra la copia del identificador sin formato, es posible que se produzca un error en una llamada a <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> posterior, porque se trate de realizar el cierre en el mismo identificador, que ahora no es válido.  
  
 Hay varias maneras en que puede producirse la duplicación incorrecta del identificador:  
  
- Busque las llamadas al método <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A>. Las llamadas a este método deben ser sumamente infrecuentes, y las que encuentre deben estar entre las llamadas a los métodos <xref:System.Runtime.InteropServices.SafeHandle.DangerousAddRef%2A> y <xref:System.Runtime.InteropServices.SafeHandle.DangerousRelease%2A>. Estos métodos especifican la región de código en la que el valor de identificador sin formato se puede utilizar de forma segura. Fuera de esta región o si, de entrada, el número de referencias no se incrementa nunca, el valor de identificador se puede invalidar en cualquier momento con una llamada a <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A> o <xref:System.Runtime.InteropServices.SafeHandle.Close%2A> en otro subproceso. Después de encontrar todos los usos de <xref:System.Runtime.InteropServices.SafeHandle.DangerousGetHandle%2A>, debe seguir la ruta de acceso que toma el identificador sin formato, para comprobar que no se entregue a otro componente que podría terminar llamando a `CloseHandle` o a otro método nativo de bajo nivel que libere el identificador.  
  
- Asegúrese de que el código que se usa para inicializar <xref:System.Runtime.InteropServices.SafeHandle> con un valor de identificador sin procesar válido posee el identificador. Si crea un <xref:System.Runtime.InteropServices.SafeHandle> alrededor de un identificador que no es propiedad del código sin establecer el parámetro `ownsHandle` como `false` en el constructor base, tanto el <xref:System.Runtime.InteropServices.SafeHandle> como el propietario del identificador real pueden tratar de cerrar el identificador. Esto provocará un error en <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> si el <xref:System.Runtime.InteropServices.SafeHandle> llega más tarde.  
  
- Cuando se calculen las referencias de <xref:System.Runtime.InteropServices.SafeHandle> entre los dominios de aplicación, confirme que la derivación de <xref:System.Runtime.InteropServices.SafeHandle> que se usa se marcó como serializable. En los casos poco frecuentes en que una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> se hizo serializable, esta debería implementar la interfaz de <xref:System.Runtime.Serialization.ISerializable> o utilizar una de las otras técnicas para controlar los procesos de serialización y deserialización manualmente. Es necesario hacer esto porque la acción de serialización predeterminada consiste en crear un clon bit a bit del valor de identificador sin formato delimitado, lo que genera dos instancias de <xref:System.Runtime.InteropServices.SafeHandle> que creen que poseen el mismo identificador. Ambas tratarán de llamar a <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> en el mismo identificador en algún momento. En la segunda <xref:System.Runtime.InteropServices.SafeHandle> que lo haga, se producirá un error. El procedimiento que se debe seguir al serializar un <xref:System.Runtime.InteropServices.SafeHandle> es llamar a la función `DuplicateHandle` o a una función similar del tipo de identificador nativo para crear una copia del identificador legal y distintiva. Si su tipo de identificador no admite esto, el tipo de <xref:System.Runtime.InteropServices.SafeHandle> que lo contiene no se puede hacer serializable.  
  
- Se puede realizar un seguimiento de las ocasiones en que un identificador se cierra pronto, lo que produce un error al llamar finalmente al método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>. Para ello, se debe colocar un punto de interrupción del depurador en la rutina nativa que se usa para liberar el identificador como, por ejemplo, la función `CloseHandle`. Esto puede no ser posible en los escenarios de esfuerzo o, incluso, en las pruebas funcionales de tamaño medio, debido a la intensidad del tráfico que suelen afrontar esas rutinas. Puede ser útil para instrumentar el código que llama al método de liberación nativo, con el fin de capturar la identidad del llamador o, posiblemente, un seguimiento completo de la pila, y el valor del identificador que se libera.  El valor del identificador puede compararse con el valor indicado por este MDA.  
  
- Tenga en cuenta que algunos tipos de identificador nativo como, por ejemplo, todos los identificadores de Win32 que se pueden liberar con la función `CloseHandle`, comparten el mismo espacio de nombres de identificador. Si un tipo de identificador se libera por error, puede producir problemas con otro. Por ejemplo, si un identificador de evento de Win32 se cierra accidentalmente dos veces, puede hacer que un identificador de archivos aparentemente no relacionado se cierre de forma prematura. Esto ocurre cuando se libera el identificador y el valor del identificador pasa a estar disponible para realizar el seguimiento de otro recurso, que puede ser de otro tipo. Si esto sucede y se produce otra liberación errónea, es posible que se invalide el identificador de un subproceso no relacionado.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Output  
 Un mensaje que indica que un <xref:System.Runtime.InteropServices.SafeHandle> o un <xref:System.Runtime.InteropServices.CriticalHandle> no pudieron liberar correctamente el identificador. Por ejemplo:  
  
```output
"A SafeHandle or CriticalHandle of type 'MyBrokenSafeHandle'   
failed to properly release the handle with value 0x0000BEEF. This   
usually indicates that the handle was released incorrectly via   
another means (such as extracting the handle using DangerousGetHandle   
and closing it directly or building another SafeHandle around it."  
```  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <releaseHandleFailed/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra un ejemplo de código que puede activar el MDA de `releaseHandleFailed`.  
  
```csharp
bool ReleaseHandle()  
{  
    // Calling the Win32 CloseHandle function to release the   
    // native handle wrapped by this SafeHandle. This method returns   
    // false on failure, but should only fail if the input is invalid   
    // (which should not happen here). The method specifically must not   
    // fail simply because of lack of resources or other transient   
    // failures beyond the user’s control. That would make it unacceptable   
    // to call CloseHandle as part of the implementation of this method.  
    return CloseHandle(handle);  
}  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización para interoperabilidad](../interop/interop-marshaling.md)
