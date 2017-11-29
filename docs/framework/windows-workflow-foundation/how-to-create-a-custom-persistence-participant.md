---
title: "Cómo: Crear un participante de persistencia personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c690a0233a425a706ead7441447f589d8330bc0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Cómo: Crear un participante de persistencia personalizado
El siguiente procedimiento describe los pasos para crear un participante de persistencia. Consulte la [participa en la persistencia](http://go.microsoft.com/fwlink/?LinkID=177735) ejemplo y [extensibilidad del almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) tema para las implementaciones de ejemplo de participantes de persistencia.  
  
1.  Cree una clase que derive de la clase <xref:System.Activities.Persistence.PersistenceParticipant> o <xref:System.Activities.Persistence.PersistenceIOParticipant>. La clase PersistenceIOParticipant proporciona los mismos puntos de extensibilidad que la clase PersistenceParticipant además de poder participar en operaciones de E/S. Siga uno o varios de los pasos siguientes:  
  
2.  Implemente el método <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. El **CollectValues** método tiene dos parámetros de diccionario, uno para almacenar los valores de lectura/escritura y el otro para almacenar los valores de solo escritura (se usa después en consultas). En este método, debería rellenar estos diccionarios con datos que sean específicos de un participante de persistencia. Cada diccionario contiene el nombre del valor como clave y el propio valor como un objeto <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
     Los valores en el diccionario de readWriteValues se empaquetan como **InstanceValue** objetos. Los valores del diccionario de solo escritura se empaquetan como **InstanceValue** objetos con InstanceValueOptions.Optional y InstanceValueOption.WriteOnly establecidos. Cada **InstanceValue** proporcionada por el **CollectValues** implementaciones en todos los participantes de persistencia deben tener un nombre único.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  Implemente el método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. El **MapValues** método toma dos parámetros que son similares a los parámetros que el **CollectValues** método recibe. Todos los valores recopilan en el **CollectValues** fase se pasan a través de estos parámetros de diccionario. Los nuevos valores agregados por el **MapValues** fase se agregan a los valores de solo escritura.  El diccionario de solo escritura se usa para proporcionar datos a un origen externo no asociado directamente a valores de la instancia. Cada valor proporcionado por implementaciones de la **MapValues** método en todos los participantes de persistencia debe tener un nombre único.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     El método <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> proporciona funcionalidad que <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> no ofrece; permite una dependencia de otro valor proporcionado por otro participante de persistencia que <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> no ha procesado todavía.  
  
4.  Implemente el **PublishValues** método. El **PublishValues** método recibe un diccionario que contiene todos los valores cargados desde el almacén de persistencia.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  Implemente el **BeginOnSave** método si el participante es un participante de E/S de persistencia. A este método se llama durante una operación de almacenamiento. En este método, debería realizar al adjunto de E/S en las instancias de flujo de trabajo de persistencia (almacenamiento).  Si el host está usando una transacción para el comando de persistencia correspondiente, se proporciona la misma transacción en Transaction.Current.  Además, PersistenceIOParticipants puede anunciar un requisito de coherencia transaccional, en cuyo caso el host crea una transacción para el episodio de persistencia si, por el contrario, no se usara uno.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Implemente el **BeginOnLoad** método si el participante es un participante de E/S de persistencia. A este método se llama durante una operación de carga. En este método, debería realizar al adjunto de E/S en la carga de instancias de flujo de trabajo. Si el host está usando una transacción para el comando de persistencia correspondiente, se proporciona la misma transacción en Transaction.Current. Además, los participantes de E/S de persistencia pueden anunciar un requisito de coherencia transaccional, en cuyo caso el host crea una transacción para el episodio de persistencia si, de lo contrario, no se usara uno.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
