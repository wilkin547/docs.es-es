---
title: "Adaptaci&#243;n de actividades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Adaptaci&#243;n de actividades
Cuando las aplicaciones y componentes del flujo de trabajo tienen el potencial para que se adapten a otras referencias culturales e idiomas, las cadenas de recurso deben usarse de manera que se puedan adaptar sin recompilar.  
  
## Adaptación de actividades  
 Tal y como ocurre con todas las aplicaciones que deben adaptarse \(distribuidas en versiones distintas para diferentes idiomas y referencias culturales\), las cadenas que se vayan a mostrar al usuario no deberían ponerse directamente en código sino que deberían almacenarse en un archivo de recursos.Será entonces cuando se podrá tener acceso a las cadenas mediante <xref:System.Environment.GetResourceString>.Si está desarrollando un componente que se distribuye en varios idiomas, querrá usar además cadenas de recursos para los mensajes de validación de actividad, datos de seguimiento definidos por el usuario, mensajes de traza y mensajes de error.  
  
 En el siguiente ejercicio se muestra cómo usar un archivo de recursos.  
  
#### Usar archivos de recursos para cadenas adaptadas  
  
1.  En [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], haga clic con el botón secundario en el proyecto en **Explorador de soluciones** y seleccione **Agregar**, **Nuevo elemento**.  
  
2.  Seleccione **Archivo de recursos** y dé un nombre al archivo ErrorResources.resx.Haga clic en **Agregar**.  
  
3.  Abra el archivo de recursos.Agregue una nueva entrada con un **nombre** de ErrorString y un **valor** de "La actividad no es válida".  
  
4.  Agregue las instrucciones `using` siguientes a su clase.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
  
    ```  
  
5.  Cree un administrador de recursos en el proyecto.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
  
    ```  
  
6.  Reciba la cadena del administrador de recursos donde sea necesaria.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
  
    ```  
  
 El siguiente ejemplo de código muestra cómo usar las cadenas adaptadas en el método <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```