---
title: Aplicaciones multiproceso (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
ms.openlocfilehash: ab4b8d1c77ae75aee6f2cf459258766f88d86abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650483"
---
# <a name="multithreaded-applications-visual-basic"></a>Aplicaciones multiproceso (Visual Basic)
Con Visual Basic, puede escribir aplicaciones que realizan varias tareas al mismo tiempo. Las tareas con la posibilidad de contener otras tareas pueden ejecutarse en subprocesos separados, lo que se conoce como *multithreading* o *subprocesamiento libre*.  
  
 Las aplicaciones que usan multithreading responden mejor a la entrada del usuario, ya que la interfaz de usuario permanece activa mientras las tareas que requieren un uso intensivo del procesador se ejecutan en subprocesos separados. El multithreading también es útil cuando se crean aplicaciones escalables, porque se pueden agregar subprocesos a medida que aumenta la carga de trabajo.  
  
## <a name="creating-and-using-threads"></a>Crear y usar subprocesos  
 Si necesita tener más control sobre el comportamiento de los subprocesos de la aplicación, puede administrar los subprocesos por su cuenta. Aun así, debe tener en cuenta que puede ser difícil escribir aplicaciones multiproceso correctas, ya que la aplicación puede dejar de responder o experimentar errores transitorios debidos a condiciones de carrera. Para obtener más información, vea [Componentes seguros para subprocesos](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Para crear un subproceso, declare una variable de tipo <xref:System.Threading.Thread> y llame al constructor. Proporcione el nombre del procedimiento o método que quiera ejecutar en el subproceso nuevo. El siguiente código proporciona un ejemplo.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Iniciar y detener subprocesos  
 Para iniciar la ejecución de un subproceso nuevo, use el método <xref:System.Threading.Thread.Start%2A>, como se muestra en el código siguiente.  
  
```vb  
newThread.Start()  
```  
  
 Para detener la ejecución de un subproceso, use el método <xref:System.Threading.Thread.Abort%2A>, como se muestra en el código siguiente.  
  
```vb  
newThread.Abort()  
```  
  
 Además de iniciar y detener los subprocesos, también puede pausarlos llamando al método <xref:System.Threading.Thread.Sleep%2A> o <xref:System.Threading.Thread.Suspend%2A>, reanudar un subproceso suspendido con el método <xref:System.Threading.Thread.Resume%2A> y destruir un subproceso con el método <xref:System.Threading.Thread.Abort%2A>.  
  
### <a name="thread-methods"></a>Métodos de subproceso  
 En la tabla siguiente se muestran algunos de los métodos que puede usar para controlar subprocesos individuales.  
  
|Método|Acción|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|Hace que un subproceso empiece a ejecutarse.|  
|<xref:System.Threading.Thread.Sleep%2A>|Detiene un subproceso durante un tiempo especificado.|  
|<xref:System.Threading.Thread.Suspend%2A>|Pausa un subproceso cuando alcanza un punto seguro.|  
|<xref:System.Threading.Thread.Abort%2A>|Detiene un subproceso cuando alcanza un punto seguro.|  
|<xref:System.Threading.Thread.Resume%2A>|Reinicia un subproceso suspendido.|  
|<xref:System.Threading.Thread.Join%2A>|Hace que el subproceso actual espere a que termine otro subproceso. En el caso de que se use con un valor de tiempo de espera, este método devuelve `True` si el subproceso termina en el tiempo asignado.|  
  
### <a name="safe-points"></a>Puntos de seguridad  
 La mayoría de estos métodos se explican por sí solos, pero el concepto de *puntos seguros* podría resultarle nuevo. Los puntos seguros son ubicaciones del código donde es seguro que Common Language Runtime realice una *recolección de elementos no utilizados* automática, un proceso que consiste en liberar variables no usadas y reclamar memoria. Cuando se llama al método <xref:System.Threading.Thread.Abort%2A> o <xref:System.Threading.Thread.Suspend%2A> de un subproceso, Common Language Runtime analiza el código y determina una ubicación adecuada en la que el subproceso puede dejar de ejecutarse.  
  
### <a name="thread-properties"></a>Propiedades del subproceso  
 Los subprocesos también contienen varias propiedades útiles, como se muestra en la tabla siguiente:  
  
|Property|Valor|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Contiene el valor `True` si un subproceso está activo.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Obtiene o establece un valor booleano que indica si un subproceso es o debe ser un subproceso en segundo plano. Los subprocesos en segundo plano son como subprocesos en primer plano, con la diferencia de que un subproceso en segundo plano no impide que un proceso se detenga. Una vez que se hayan detenido todos los subprocesos en primer plano que pertenecen a un proceso, Common Language Runtime finaliza el proceso mediante una llamada al método <xref:System.Threading.Thread.Abort%2A> en los subprocesos en segundo plano que continúan activos.|  
|<xref:System.Threading.Thread.Name%2A>|Obtiene o establece el nombre de un subproceso. Suele usarse para detectar subprocesos individuales durante la depuración.|  
|<xref:System.Threading.Thread.Priority%2A>|Obtiene o establece un valor que el sistema operativo usa para dar prioridad a la programación de subprocesos.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Contiene un valor que describe los estados de un subproceso.|  
  
## <a name="thread-priorities"></a>Prioridades de subprocesos  
 Cada subproceso tiene una propiedad de prioridad que determina la cantidad de tiempo de procesador que tiene que ejecutar. El sistema operativo asigna tiempos mayores a los subprocesos de alta prioridad y tiempos menores a los subprocesos de baja prioridad. Se crean subprocesos con el valor de `Normal`, pero puede cambiar la propiedad <xref:System.Threading.Thread.Priority%2A> a cualquier valor en la enumeración <xref:System.Threading.ThreadPriority>.  
  
 Vea <xref:System.Threading.ThreadPriority> para obtener una descripción detallada de las diversas prioridades de subprocesos.  
  
## <a name="foreground-and-background-threads"></a>Subprocesos de primer y segundo plano  
 Un *subproceso en primer plano* se ejecuta de forma indefinida, mientras que un *subproceso en segundo plano* se detiene en el momento en que se detiene el último subproceso en primer plano. Puede usar la propiedad <xref:System.Threading.Thread.IsBackground%2A> para determinar o cambiar el estado en segundo plano de un subproceso.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
