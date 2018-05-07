---
title: Adaptación de actividades
ms.date: 03/30/2017
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
ms.openlocfilehash: 23a6d5c2ed202f030397eb70382896468a68a724
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="activity-localization"></a>Adaptación de actividades
Cuando las aplicaciones y componentes del flujo de trabajo tienen el potencial para que se adapten a otras referencias culturales e idiomas, las cadenas de recurso deben usarse de manera que se puedan adaptar sin recompilar.  
  
## <a name="activity-localization"></a>Adaptación de actividades  
 Tal y como ocurre con todas las aplicaciones que deben adaptarse (distribuidas en versiones distintas para diferentes idiomas y referencias culturales), las cadenas que se vayan a mostrar al usuario no deberían ponerse directamente en código sino que deberían almacenarse en un archivo de recursos. Las cadenas, a continuación, pueden tener acceso mediante <!--zz <xref:System.Environment.GetResourceString> --> `GetResourceString`. Si está desarrollando un componente que se distribuye en varios idiomas, querrá usar además cadenas de recursos para los mensajes de validación de actividad, datos de seguimiento definidos por el usuario, mensajes de traza y mensajes de error.  
  
 En el siguiente ejercicio se muestra cómo usar un archivo de recursos.  
  
#### <a name="using-resource-files-for-localized-strings"></a>Usar archivos de recursos para cadenas adaptadas  
  
1.  En [!INCLUDE[vs2010](../../../includes/vs2010-md.md)], haga clic en el proyecto en **el Explorador de soluciones** y seleccione **agregar...** , **Nuevo elemento...** .  
  
2.  Seleccione **archivo de recursos** y un nombre al archivo ErrorResources.resx. Haga clic en **Agregar**.  
  
3.  Abra el archivo de recursos. Agregar una nueva entrada con un **nombre** de ErrorString y un **valor** de "la actividad no es válida".  
  
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
