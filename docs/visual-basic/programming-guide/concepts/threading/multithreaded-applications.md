---
title: Aplicaciones multiproceso (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5bde7f49a2f2bc8a2e6c1eeab3722428b8a37a95
ms.lasthandoff: 03/13/2017

---
# <a name="multithreaded-applications-visual-basic"></a>Aplicaciones multiproceso (Visual Basic)
Con Visual Basic, puede escribir aplicaciones que realizan varias tareas al mismo tiempo. Las tareas con la posibilidad de mantener otras tareas pueden ejecutarse en subprocesos separados, un proceso conocido como *multithreading* o *libre subprocesamiento*.  
  
 Las aplicaciones que utilizan multithreading son más sensibles a la entrada del usuario, porque la interfaz de usuario permanece activa cuando se ejecutan las tareas de uso intensivo del procesador en subprocesos separan. El multithreading también es útil cuando se crean aplicaciones escalables, porque se pueden agregar subprocesos a medida que aumenta la carga de trabajo.  
  
## <a name="creating-and-using-threads"></a>Crear y usar subprocesos  
 Si necesita más control sobre el comportamiento de los subprocesos de la aplicación, puede administrar los subprocesos. Sin embargo, tenga en cuenta que escribir aplicaciones multiproceso correctas puede ser difícil: la aplicación puede dejar de responder o experimentar errores transitorios debido a condiciones de carrera. Para obtener más información, consulte [componentes seguros para subprocesos](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Crear un nuevo subproceso mediante la declaración de una variable de tipo <xref:System.Threading.Thread>y llamando al constructor, proporcionando el nombre del procedimiento o método que desea ejecutar en el subproceso nuevo.</xref:System.Threading.Thread> El siguiente código proporciona un ejemplo.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Iniciar y detener subprocesos  
 Para iniciar la ejecución de un nuevo subproceso, utilice el <xref:System.Threading.Thread.Start%2A>método, tal como se muestra en el código siguiente.</xref:System.Threading.Thread.Start%2A>  
  
```vb  
newThread.Start()  
```  
  
 Para detener la ejecución de un subproceso, utilice el <xref:System.Threading.Thread.Abort%2A>método, tal como se muestra en el código siguiente.</xref:System.Threading.Thread.Abort%2A>  
  
```vb  
newThread.Abort()  
```  
  
 Además de iniciar y detener subprocesos, también puede pausar subprocesos llamando a la <xref:System.Threading.Thread.Sleep%2A>o <xref:System.Threading.Thread.Suspend%2A>método, reanudar un subproceso suspendido mediante el <xref:System.Threading.Thread.Resume%2A>método y destruir un subproceso mediante el <xref:System.Threading.Thread.Abort%2A>método</xref:System.Threading.Thread.Abort%2A> </xref:System.Threading.Thread.Resume%2A> </xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Sleep%2A>  
  
### <a name="thread-methods"></a>Métodos de subproceso  
 La tabla siguiente muestran algunos de los métodos que puede usar para controlar subprocesos individuales.  
  
|Método|Acción|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>|Hace que un subproceso empiecen a ejecutarse.|  
|<xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>|Detiene un subproceso durante un tiempo especificado.|  
|<xref:System.Threading.Thread.Suspend%2A></xref:System.Threading.Thread.Suspend%2A>|Detiene un subproceso cuando alcanza un punto seguro.|  
|<xref:System.Threading.Thread.Abort%2A></xref:System.Threading.Thread.Abort%2A>|Detiene un subproceso cuando alcanza un punto seguro.|  
|<xref:System.Threading.Thread.Resume%2A></xref:System.Threading.Thread.Resume%2A>|Reinicia un subproceso suspendido|  
|<xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>|Hace que el subproceso actual para que espere a que termine otro subproceso. Si se utiliza con un valor de tiempo de espera, este método devuelve `True` si el subproceso termina en el tiempo asignado.|  
  
### <a name="safe-points"></a>Puntos de seguridad  
 La mayoría de estos métodos son autoexplicativos, pero el concepto de *puntos seguros* puede ser nuevo para usted. Puntos seguros son ubicaciones del código sea seguro para common language runtime realizar automática *recolección*, el proceso de liberar variables no utilizadas y reclamar memoria. Cuando se llama a la <xref:System.Threading.Thread.Abort%2A>o <xref:System.Threading.Thread.Suspend%2A>método de un subproceso, common language runtime analiza el código y determina la ubicación de una ubicación adecuada para el subproceso deje de ejecutarse.</xref:System.Threading.Thread.Suspend%2A> </xref:System.Threading.Thread.Abort%2A>  
  
### <a name="thread-properties"></a>Propiedades del subproceso  
 Los subprocesos contienen también varias propiedades útiles, como se muestra en la tabla siguiente:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A></xref:System.Threading.Thread.IsAlive%2A>|Contiene el valor `True` si un subproceso está activo.|  
|<xref:System.Threading.Thread.IsBackground%2A></xref:System.Threading.Thread.IsBackground%2A>|Obtiene o establece un valor booleano que indica si un subproceso es o debe ser un subproceso en segundo plano. Subprocesos en segundo plano son como los subprocesos de primer plano, pero un subproceso en segundo plano no evita que un proceso de detención. Una vez detengan todos los subprocesos de primer plano que pertenecen a un proceso, common language runtime finaliza el proceso llamando a la <xref:System.Threading.Thread.Abort%2A>método en subprocesos en segundo plano que continúan activos.</xref:System.Threading.Thread.Abort%2A>|  
|<xref:System.Threading.Thread.Name%2A></xref:System.Threading.Thread.Name%2A>|Obtiene o establece el nombre de un subproceso. Suelen utilizarse para descubrir subprocesos individuales durante la depuración.|  
|<xref:System.Threading.Thread.Priority%2A></xref:System.Threading.Thread.Priority%2A>|Obtiene o establece un valor que se utiliza el sistema operativo para dar prioridad a la programación de subprocesos.|  
|<xref:System.Threading.Thread.ThreadState%2A></xref:System.Threading.Thread.ThreadState%2A>|Contiene un valor que describe el estado o Estados de un subproceso.|  
  
## <a name="thread-priorities"></a>Las prioridades de subprocesos  
 Cada subproceso tiene una propiedad de prioridad que determina cómo porción de tiempo de procesador tiene que ejecutarse. El sistema operativo asigna mayores porciones de tiempo a los subprocesos de alta prioridad y menores a los subprocesos de baja prioridad. Nuevos subprocesos se crean con el valor de `Normal`, pero se puede cambiar el <xref:System.Threading.Thread.Priority%2A>propiedad a cualquier valor en el <xref:System.Threading.ThreadPriority>enumeración.</xref:System.Threading.ThreadPriority> </xref:System.Threading.Thread.Priority%2A>  
  
 Consulte <xref:System.Threading.ThreadPriority>para obtener una descripción detallada de las diversas prioridades de subprocesos.</xref:System.Threading.ThreadPriority>  
  
## <a name="foreground-and-background-threads"></a>Subprocesos de primer y segundo plano  
 Un *subproceso en primer plano* se ejecuta de forma indefinida, mientras que un *subproceso en segundo plano* se detiene en cuanto el último subproceso de primer plano se ha detenido. Puede usar el <xref:System.Threading.Thread.IsBackground%2A>propiedad para determinar o cambiar el estado de un subproceso en segundo plano.</xref:System.Threading.Thread.IsBackground%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 [Sincronización de subprocesos (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)   
 [Parámetros y valores devueltos para procedimientos multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)   
 [Subprocesamiento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
