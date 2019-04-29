---
title: Crear actividades de control de flujo personalizadas
ms.date: 03/30/2017
ms.assetid: 27f409f6-2d1d-4cfb-9765-93eb2ad667d5
ms.openlocfilehash: 2be47281335066def5c1d267cd709db5a8ff1187
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774067"
---
# <a name="creating-custom-flow-control-activities"></a>Crear actividades de control de flujo personalizadas
.NET Framework contiene una variedad de actividades de control de flujo que funcionan de forma similar a abstraer las estructuras de programación (como <xref:System.Activities.Statements.Flowchart>) o a las instrucciones de programación estándares (como <xref:System.Activities.Statements.If>). En este tema se describe la arquitectura de uno de los proyectos de ejemplo, [ForEach no genérica](./samples/non-generic-foreach.md).  
  
## <a name="creating-the-custom-class"></a>Crear la clase personalizada  
 Dado que la clase ForEach no genérica tendrá que programar actividades secundarias, será necesario que derive de <xref:System.Activities.NativeActivity>, ya que las actividades que derivan de <xref:System.Workflow.Activities.CodeActivity> no tienen esta funcionalidad.  
  
```  
public sealed class ForEach : NativeActivity  
    {  
```  
  
 La clase personalizada requiere que varios miembros almacenen datos que van a ser utilizados por la actividad y proporcionen funcionalidad para ejecutar las actividades secundarias de la actividad. Estos miembros son los siguientes:  
  
- `valueEnumerator`: No pública <xref:System.Activities.Variable%601> de tipo <xref:System.Collections.IEnumerator> utilizado para recorrer en iteración la colección de elementos. Este miembro es de tipo <xref:System.Activities.Variable%601> porque se utiliza internamente en la actividad, en lugar de un argumento o una propiedad pública, que se utilizarían si este objeto fuera a tener un origen externo a la actividad.  
  
- `OnChildComplete`: El público <xref:System.Activities.CompletionCallback> propiedad que se ejecuta cuando completa la ejecución de cada elemento secundario. Este miembro se define como una propiedad CLR, ya que su valor no cambiará para las diferentes instancias de la actividad.  
  
- `Values`: La colección de entradas que se utilizan para las iteraciones de la actividad secundaria. Este miembro es de tipo <xref:System.Activities.InArgument%601>, ya que el origen de los datos es externo a la actividad, pero no se espera que el contenido de la colección cambie durante la ejecución de la actividad. Si la actividad necesitara que la funcionalidad cambiara el contenido de esta colección durante su ejecución (para agregar o quitar actividades, por ejemplo), este miembro se habría definido como <xref:System.Activities.ActivityAction>, y se habría evaluado cada vez que se hubiera tenido acceso a él, de modo que los cambios estuvieran disponibles para la actividad.  
  
- `Body`: Este miembro define la actividad que se ejecutará para cada elemento de la `Values` colección. Se define como <xref:System.Activities.ActivityAction> para que se evalúe cada vez que se tenga acceso a él.  
  
- `Execute`: Este método usa la `InternalExecute`, `OnForEachComplete`, y `GetStateAndExecute` miembros no públicos para programar la ejecución y asignar el controlador de finalización de la actividad secundaria definida en el miembro Body.  
  
- `CacheMetadata`: Este miembro proporciona el tiempo de ejecución con la información que necesita para ejecutar la actividad. De forma predeterminada, el método `CacheMetadata` de una actividad informará al runtime de todos los miembros públicos de la actividad, pero como esta actividad utiliza miembros privados para alguna funcionalidad, necesita informar al runtime de su existencia para que este los tenga en cuenta. En este caso, la función `CacheMetadata` se reemplaza para que se pueda tener acceso al miembro `valueEnumerator` privado. Este miembro también crea un argumento para los valores de la actividad de modo que se puedan pasar a la actividad durante la ejecución.
