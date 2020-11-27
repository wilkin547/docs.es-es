---
title: Procedimiento para crear un participante de persistencia personalizado
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 633961ac12eed593613eba75862cbc81f2fa68c6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275819"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Procedimiento para crear un participante de persistencia personalizado

El siguiente procedimiento describe los pasos para crear un participante de persistencia. Vea el tema [participar en](/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100)) el ejemplo de persistencia y [extensibilidad del almacén](store-extensibility.md) para obtener implementaciones de ejemplo de participantes de persistencia.  
  
1. Cree una clase que derive de la clase <xref:System.Activities.Persistence.PersistenceParticipant> o <xref:System.Activities.Persistence.PersistenceIOParticipant>. La clase PersistenceIOParticipant proporciona los mismos puntos de extensibilidad que la clase PersistenceParticipant, además de poder participar en operaciones de e/s. Siga uno o varios de los pasos siguientes:  
  
2. Implemente el método <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. El método **CollectValues** tiene dos parámetros de diccionario, uno para almacenar los valores de lectura/escritura y otro para almacenar los valores de solo escritura (se usa más adelante en las consultas). En este método, debería rellenar estos diccionarios con datos que sean específicos de un participante de persistencia. Cada diccionario contiene el nombre del valor como clave y el propio valor como un objeto <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
    Los valores del diccionario readWriteValues se empaquetan como objetos **InstanceValue** . Los valores del Diccionario de solo escritura se empaquetan como objetos **InstanceValue** con InstanceValueOptions. Optional y InstanceValueOption. WriteOnly set. Cada **InstanceValue** proporcionado por las implementaciones de **CollectValues** en todos los participantes de persistencia debe tener un nombre único.
  
    ```csharp  
    protected virtual void CollectValues(out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
3. Implemente el método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. El método **MapValues** toma dos parámetros que son similares a los parámetros que recibe el método **CollectValues** . Todos los valores recopilados en la fase **CollectValues** se pasan a través de estos parámetros del diccionario. Los nuevos valores agregados por la fase **MapValues** se agregan a los valores de solo escritura.  El diccionario de solo escritura se usa para proporcionar datos a un origen externo no asociado directamente a valores de la instancia. Cada valor proporcionado por implementaciones del método **MapValues** en todos los participantes de persistencia debe tener un nombre único.  
  
    ```csharp  
    protected virtual IDictionary<XName,Object> MapValues(IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
     El método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> proporciona funcionalidad que <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> no ofrece; permite una dependencia de otro valor proporcionado por otro participante de persistencia que <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> no ha procesado todavía.  
  
4. Implemente el método **PublishValues** . El método **PublishValues** recibe un diccionario que contiene todos los valores cargados desde el almacén de persistencia.  
  
    ```csharp  
    protected virtual void PublishValues(IDictionary<XName,Object> readWriteValues)
    {
    }
    ```  
  
5. Implemente el método **método beginonsave** si el participante es un participante de e/s de persistencia. A este método se llama durante una operación de almacenamiento. En este método, debe realizar complemento de e/s en las instancias de flujo de trabajo persistentes (guardando).  Si el host está usando una transacción para el comando de persistencia correspondiente, se proporciona la misma transacción en Transaction.Current.  Además, PersistenceIOParticipants puede anunciar un requisito de coherencia transaccional, en cuyo caso el host crea una transacción para el episodio de persistencia si, por el contrario, no se usara uno.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnSave(IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```  
  
6. Implemente el método **BeginOnLoad** si el participante es un participante de e/s de persistencia. A este método se llama durante una operación de carga. En este método, debe realizar una complemento de e/s a la carga de las instancias de flujo de trabajo. Si el host está usando una transacción para el comando de persistencia correspondiente, se proporciona la misma transacción en Transaction.Current. Además, los participantes de e/s de persistencia pueden anunciar un requisito de coherencia transaccional, en cuyo caso el host crea una transacción para el episodio de persistencia, en caso contrario, si no se utilizara una.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnLoad(IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```
