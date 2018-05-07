---
title: Patrón de Dispose
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcb746ae2d8c2262b0cd0c6c9dcaababb12bd63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dispose-pattern"></a>Patrón de Dispose
Todos los programas adquieren uno o más recursos del sistema, como la memoria, los identificadores del sistema o las conexiones de base de datos, en el transcurso de su ejecución. Los desarrolladores tienen que tenga cuidado al usar estos recursos del sistema, porque debe liberarse después de adquirir y usar.  
  
 CLR proporciona compatibilidad para la administración automática de la memoria. La memoria administrada (memoria asignada mediante el operador de C# `new`) no es necesario liberar de forma explícita. Se liberan automáticamente por el recolector de elementos no utilizados (GC). Esto evita que los desarrolladores la tarea tediosa y difícil de liberación de memoria y ha sido una de las razones principales para la productividad sin precedentes ofrecida por .NET Framework.  
  
 Desafortunadamente, la memoria administrada es solo uno de muchos tipos de recursos del sistema. Aún así, los recursos distintos de la memoria administrada deben liberar explícitamente y se conocen como recursos no administrados. El catálogo global concreto no se diseñó para administrar estos recursos no administrados, lo que significa que la responsabilidad de administrar los recursos no administrados que se encuentra en manos de los desarrolladores.  
  
 El CLR proporciona ayuda en liberar recursos no administrados. <xref:System.Object?displayProperty=nameWithType> declara un método virtual <xref:System.Object.Finalize%2A> (también denominado el finalizador) que es llamado por el catálogo global antes de la memoria del objeto sea reclamada por el catálogo global y se puede invalidar para liberar recursos no administrados. Los tipos que invalidan el finalizador se conocen como tipos susceptibles de finalización.  
  
 Aunque los finalizadores son eficaces en algunos escenarios de limpieza, tienen dos desventajas importantes:  
  
-   El finalizador se llama cuando el GC detecta que un objeto es apto para la recolección. Esto sucede durante un período indeterminado de tiempo después de que el recurso no es necesaria ya. El retraso entre cuando el desarrollador puede o desea liberar el recurso y la hora cuando el recurso se libera realmente por el finalizador podría ser aceptable en programas que adquieren muchos recursos insuficientes (recursos que se pueden agotar fácilmente) o en casos en que los recursos son costosos mantener en uso (p. ej., los búferes de gran cantidad de memoria no administrada).  
  
-   Cuando el CLR necesita llamar a un finalizador, debe posponer esta acción de la memoria del objeto hasta que la siguiente de ida y vuelta de recolección de elementos (los finalizadores ejecutar entre colecciones). Esto significa que la memoria del objeto (y todos los objetos que se hace referencia a) no se disocie durante un período más largo de tiempo.  
  
 Por lo tanto, basarse exclusivamente en los finalizadores podría no ser apropiado en muchos escenarios cuando es importante reclamar los recursos no administrados lo más rápido posible, cuando se trabaja con recursos insuficientes, o en escenarios de alta un rendimiento superior en el que la sobrecarga adicional de GC de finalización no es aceptable.  
  
 El marco de trabajo proporciona el <xref:System.IDisposable?displayProperty=nameWithType> interfaz que debe implementarse para proporcionar a los programadores un método manual para liberar recursos no administrados como no son necesarios. También proporciona la <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> método que puede indicar el catálogo global que un objeto se ha eliminado manualmente y no necesita ser finalizados ya, en cuyo caso se puede reclamar la memoria del objeto anterior. Los tipos que implementan la `IDisposable` interfaz se conocen como tipos descartables.  
  
 El patrón Dispose está diseñado para estandarizar el uso y la implementación de los finalizadores y el `IDisposable` interfaz.  
  
 La motivación principal para el patrón es reducir la complejidad de la implementación de la <xref:System.Object.Finalize%2A> y <xref:System.IDisposable.Dispose%2A> métodos. La complejidad proviene del hecho de que los métodos comparten algunos, pero no todas las rutas de acceso de código (las diferencias se describen más adelante en el capítulo). Además, existen motivos históricos para algunos de los elementos del modelo relacionados con la evolución de la compatibilidad de idioma para la administración de recursos determinista.  
  
 **✓ HACER** implementar el patrón de Dispose básico en tipos que contiene instancias de los tipos descartables. Consulte la [patrón de Dispose básico](#basic_pattern) sección para obtener más información sobre el patrón básico.  
  
 Si un tipo es responsable de la duración de otros objetos descartables, los desarrolladores necesitan una manera para deshacerse de ellos, demasiado. Uso del contenedor `Dispose` método es una manera cómoda para que esto sea posible.  
  
 **✓ HACER** implementar el patrón Dispose básico y se proporciona un finalizador en tipos que contiene recursos que deben ser liberados explícitamente y que no tienen los finalizadores.  
  
 Por ejemplo, el modelo debe implementarse en tipos de almacenamiento de los búferes de memoria no administrada. El [tipos susceptibles de finalización](#finalizable_types) sección describe directrices relacionadas con la implementación de los finalizadores.  
  
 **✓ Considere la posibilidad de** implementar el patrón de Dispose básicas en las clases que ellos mismos no mantenga los recursos no administrados o los objetos descartables pero están probables que tienen subtipos que realizar.  
  
 Un buen ejemplo de esto es la <xref:System.IO.Stream?displayProperty=nameWithType> clase. Aunque es una clase base abstracta que no contiene todos los recursos, no de la mayoría de sus subclases y por este motivo, implementa este patrón.  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a>Patrón de Dispose básica  
 La implementación básica del patrón, es preciso implementar la `System.IDisposable` interfaz y declarar la `Dispose(bool)` método que implementa la lógica de limpieza de todos los recursos que deban compartirse entre el `Dispose` método y el finalizador opcional.  
  
 En el ejemplo siguiente se muestra una implementación simple del patrón básico:  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder(){  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        if (disposing){  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 El parámetro booleano `disposing` indica si el método se invoca desde la `IDisposable.Dispose` implementación o desde el finalizador. El `Dispose(bool)` implementación debe comprobar el parámetro antes de obtener acceso a otros objetos de referencia (por ejemplo, el campo de recursos en el ejemplo anterior). Solo se deben acceder a estos objetos cuando se llama al método desde el `IDisposable.Dispose` implementación (cuando el `disposing` parámetro es igual a true). Si el método se invoca desde el finalizador (`disposing` es false), no se deben tener acceso a otros objetos. La razón es que los objetos se finalizan en un orden impredecible y por lo tanto, o cualquiera de sus dependencias, podría haber finalizado.  
  
 Además, esta sección se aplica a las clases con una base de que ya no implementan el patrón Dispose. Si se hereda de una clase que ya implementa el patrón, invalide el `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.  
  
 **✓ HACER** declarar un `protected virtual void Dispose(bool disposing)` relacionado de método para centralizar toda la lógica para liberar recursos no administrados.  
  
 Todos los recursos deben limpiarse en este método. Se llama al método desde el finalizador de ambos y `IDisposable.Dispose` método. El parámetro será false si se va a invocar desde dentro de un finalizador. Se debe usar para asegurarse de que cualquier código que se ejecuta durante la finalización no se tiene acceso a otros objetos susceptibles de finalización. Detalles de la implementación de los finalizadores se describen en la sección siguiente.  
  
```  
protected virtual void Dispose(bool disposing){  
    if (disposing){  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 **✓ HACER** implementar la `IDisposable` interfaz llamando simplemente `Dispose(true)` seguido de `GC.SuppressFinalize(this)`.  
  
 La llamada a `SuppressFinalize` solo deberían producirse si `Dispose(true)` se ejecuta correctamente.  
  
```  
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 **X DO NOT** realizar sin parámetros `Dispose` método virtual.  
  
 El `Dispose(bool)` método es el que debe reemplazarse por las subclases.  
  
```  
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose(){ ... }  
    protected virtual void Dispose(bool disposing){ ... }  
}  
```  
  
 **X DO NOT** declarar las sobrecargas de la `Dispose` otro método que `Dispose()` y `Dispose(bool)`.  
  
 `Dispose` debe considerarse una palabra reservada para ayudar a codificar este patrón y evitar la confusión entre los implementadores y los usuarios, los compiladores. Algunos lenguajes pueden optar por implementar automáticamente este patrón de determinados tipos.  
  
 **✓ HACER** permitir la `Dispose(bool)` método al que llamar más de una vez. El método puede optar por no hacer nada después de la primera llamada.  
  
```  
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **X evitar** producir una excepción desde `Dispose(bool)` excepto en situaciones críticas que se ha dañado el proceso que lo contiene (pérdidas, un estado compartido incoherente, etcetera).  
  
 Los usuarios esperan que una llamada a `Dispose` no generará una excepción.  
  
 Si `Dispose` podría producir una excepción, no se ejecutará más lógica de limpieza del bloque finally. Para resolver este problema, el usuario necesitaría ajustar todas las llamadas a `Dispose` (en el bloque finally!) en un bloque try, lo que conduce a controladores de limpieza muy complejos. Si ejecuta un `Dispose(bool disposing)` método, nunca inician una excepción si la eliminación es false. Si lo hace, se terminará el proceso si la ejecución dentro de un contexto de finalizador.  
  
 **✓ HACER** producir una <xref:System.ObjectDisposedException> de cualquier miembro que no se puede utilizar una vez que se ha eliminado el objeto.  
  
```  
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething(){  
           if(disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
            ...  
    }  
    protected virtual void Dispose(bool disposing){  
        if(disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 **✓ Considere la posibilidad de** proporciona el método `Close()`, además el `Dispose()`, si es cerrar terminología estándar en el área.  
  
 Al hacerlo, es importante que realice la `Close` idéntico de la implementación `Dispose` y considere implementar la `IDisposable.Dispose` método explícitamente.  
  
```  
public class Stream : IDisposable {  
    IDisposable.Dispose(){  
        Close();  
    }  
    public void Close(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a>Tipos susceptibles de finalización  
 Los tipos susceptibles de finalización son tipos que extienden el patrón Dispose básico reemplazando el finalizador y proporcionar la ruta de acceso de código de finalización en la `Dispose(bool)` método.  
  
 Los finalizadores son considerablemente difíciles de implementar correctamente, principalmente porque no se realizan determinadas suposiciones (suele ser válidos) sobre el estado del sistema durante su ejecución. Las instrucciones siguientes deben tenerse en consideración cuidadosa.  
  
 Tenga en cuenta que algunas de las instrucciones se aplican no solo a los `Finalize` (método), pero en cualquier código llamar desde un finalizador. En el caso del Dispose patrón básico definido anteriormente, esto significa lógica que se ejecute dentro de `Dispose(bool disposing)` cuando el `disposing` del parámetro es false.  
  
 Si la clase base ya está susceptibles de finalización e implementa el patrón Dispose básico, no debe invalidar `Finalize` nuevo. En su lugar, debería invalidar simplemente la `Dispose(bool)` método para proporcionar lógica de limpieza de recursos adicionales.  
  
 El código siguiente muestra un ejemplo de un tipo susceptibles de finalización:  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder(){  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing){  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing){ // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    public void Dispose(){  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 **X evitar** realicen tipos susceptibles de finalización.  
  
 Tenga en cuenta todos los casos en que cree que es necesario un finalizador. Hay un número real los costos asociados con instancias con los finalizadores, desde la perspectiva de complejidad de un código y el rendimiento. Prefiere con contenedores de recursos como <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos no administrados que siempre que sea posible, en cuyo caso un finalizador se convierte en innecesario porque el contenedor es responsable de su propia limpieza de recursos.  
  
 **X DO NOT** que los tipos de valor susceptibles de finalización.  
  
 Solo los tipos de referencia realmente obtengan finalizados CLR y, por tanto, se pasará por alto cualquier intento para colocar un finalizador en un tipo de valor. Los compiladores de C++ y C# aplican esta regla.  
  
 **✓ HACER** que un tipo susceptibles de finalización si el tipo es responsable de liberar un recurso no administrado que no tiene su propio finalizador.  
  
 Al implementar el finalizador, basta con llamar a `Dispose(false)` y coloque toda la lógica de limpieza de recursos dentro de la `Dispose(bool disposing)` método.  
  
```  
public class ComplexResourceHolder : IDisposable {  
  
    ~ ComplexResourceHolder(){  
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing){  
        ...  
    }  
}  
```  
  
 **✓ HACER** implementar el patrón de Dispose básico en todos los tipos susceptibles de finalización.  
  
 Esto proporciona a los usuarios del tipo de medio para realizar explícitamente una limpieza determinista de los mismos recursos que es responsable el finalizador.  
  
 **X DO NOT** tener acceso a los objetos susceptibles de finalización en la ruta de acceso del código de finalizador, porque no hay riesgo significativo que ya habrá finalizados.  
  
 Por ejemplo, un objeto susceptible de finalización A que tiene una referencia a otro objeto susceptibles de finalización B confiable no puede usar B en del finalizador, o viceversa. Los finalizadores se llaman en orden aleatorio (aparte de una garantía de ordenación débil de finalización crítica).  
  
 Además, tenga en cuenta que estos objetos almacenados en variables estáticas se se recopilan en ciertos puntos durante una descarga del dominio de aplicación o al salir del proceso. Obtener acceso a una variable estática que hace referencia a un objeto susceptible de finalización (o llamar a un método estático que puedan usar los valores almacenados en variables estáticas) podría no ser seguro if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> devuelve true.  
  
 **✓ HACER** realizar su `Finalize` método protegido.  
  
 Los desarrolladores de C#, C++ y VB.NET no tiene que preocuparse sobre esto, porque los compiladores de ayudan a aplicar esta directriz.  
  
 **X DO NOT** escape permiten excepciones de la lógica de finalizador, excepto los errores críticos del sistema.  
  
 Si se produce una excepción de un finalizador, el CLR se apagará de todo el proceso (a partir de .NET Framework versión 2.0), impide que otros finalizadores ejecutar y recursos de que se liberan de una manera controlada.  
  
 **✓ Considere la posibilidad de** crear y usar un objeto susceptibles de finalización crítico (un tipo con una jerarquía de tipos que contiene <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) para situaciones en que un finalizador absolutamente debe ejecutar incluso frente a la fuerza del dominio de aplicación forzada y subprocesos se anula.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)  
 [Patrones de diseño comunes](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 [Recolección de elementos no utilizados](../../../docs/standard/garbage-collection/index.md)
