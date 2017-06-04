---
title: "How to: Map HRESULTs and Exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "interoperation with unmanaged code, HRESULTs"
  - "exceptions, HRESULTs"
  - "interoperation with unmanaged code, exceptions"
  - "HRESULTs"
  - "COM interop, HRESULTs"
  - "COM interop, exceptions"
ms.assetid: 610b364b-2761-429d-9c4a-afbc3e66f1b9
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Map HRESULTs and Exceptions
Los métodos COM informan de los errores devolviendo resultados HRESULT, mientras que los métodos .NET lo hacen produciendo excepciones.  El motor en tiempo de ejecución controla la transición entre ambos.  Cada clase de excepción de .NET Framework se asigna a un resultado HRESULT.  
  
 Las clases de excepción definidas por el usuario pueden especificar el resultado HRESULT que sea adecuado.  Estas clases de excepción pueden cambiar dinámicamente el resultado HRESULT que se devolverá cuando se genere la excepción estableciendo el campo **HResult** en el objeto de excepción.  El cliente recibe información adicional acerca de la excepción mediante la interfaz **IErrorInfo**, que se implementa en el objeto .NET en el proceso no administrado.  
  
 Si se crea una clase que extiende **System.Exception**, se debe establecer el campo HRESULT en el momento de la creación.  De lo contrario, el valor HRESULT lo asigna la clase base.  A un resultado HRESULT existente se le pueden asignar nuevas clases de excepción proporcionando el valor en el constructor de la excepción.  
  
 Observe que el motor en tiempo de ejecución a veces omitirá `HRESULT` en los casos en los que exista `IErrorInfo` en el subproceso.  Este comportamiento se puede producir en los casos en los que `HRESULT` y `IErrorInfo` no representen el mismo error.   ``  
  
### Crear una nueva clase de excepción y asignarla a un HRESULT  
  
1.  Utilice el código siguiente para crear una nueva clase de excepción llamada `NoAccessException` y asignarla al HRESULT `E_ACCESSDENIED`.  
  
    ```cpp  
    Class NoAccessException : public ApplicationException  
    {  
        NoAccessException () {  
        HResult = E_ACCESSDENIED;   
    }  
    }  
    CMyClass::MethodThatThrows  
    {  
    throw new NoAccessException();  
    }  
    ```  
  
 Puede haber algún programa \(en cualquier lenguaje de programación\) que use código administrado y no administrado a la vez.  Por ejemplo, el contador de referencias personalizado del ejemplo de código siguiente usa el método **Marshal.ThrowExceptionForHR\(int HResult\)** para producir una excepción con un valor específico de HRESULT.  El método busca el resultado HRESULT y genera el tipo de excepción adecuado.  Así, el resultado HRESULT del siguiente fragmento de código genera **ArgumentException**.  
  
```cpp  
CMyClass::MethodThatThrows  
{  
    Marshal.ThrowExceptionForHR(COR_E_ARGUMENT);  
}  
```  
  
 En la tabla siguiente se proporcionan todas las asignaciones de cada resultado HRESULT a su clase de excepción correspondiente en .NET Framework.  
  
|HRESULT|Excepción .NET|  
|-------------|--------------------|  
|**MSEE\_E\_APPDOMAINUNLOADED**|**AppDomainUnloadedException**|  
|**COR\_E\_APPLICATION**|**ApplicationException**|  
|**COR\_E\_ARGUMENT o E\_INVALIDARG**|**ArgumentException**|  
|**COR\_E\_ARGUMENTOUTOFRANGE**|**ArgumentOutOfRangeException**|  
|**COR\_E\_ARITHMETIC o ERROR\_ARITHMETIC\_OVERFLOW**|**ArithmeticException**|  
|**COR\_E\_ARRAYTYPEMISMATCH**|**ArrayTypeMismatchException**|  
|**COR\_E\_BADIMAGEFORMAT o ERROR\_BAD\_FORMAT**|**BadImageFormatException**|  
|**COR\_E\_COMEMULATE\_ERROR**|**COMEmulateException**|  
|**COR\_E\_CONTEXTMARSHAL**|**ContextMarshalException**|  
|**COR\_E\_CORE**|**CoreException**|  
|**NTE\_FAIL**|**CryptographicException**|  
|**COR\_E\_DIRECTORYNOTFOUND o ERROR\_PATH\_NOT\_FOUND**|**DirectoryNotFoundException**|  
|**COR\_E\_DIVIDEBYZERO**|**DivideByZeroException**|  
|**COR\_E\_DUPLICATEWAITOBJECT**|**DuplicateWaitObjectException**|  
|**COR\_E\_ENDOFSTREAM**|**EndOfStreamException**|  
|**COR\_E\_TYPELOAD**|**EntryPointNotFoundException**|  
|**COR\_E\_EXCEPTION**|**Excepción**|  
|**COR\_E\_EXECUTIONENGINE**|**ExecutionEngineException**|  
|**COR\_E\_FIELDACCESS**|**FieldAccessException**|  
|**COR\_E\_FILENOTFOUND o ERROR\_FILE\_NOT\_FOUND**|**FileNotFoundException**|  
|**COR\_E\_FORMAT**|**FormatException**|  
|**COR\_E\_INDEXOUTOFRANGE**|**IndexOutOfRangeException**|  
|**COR\_E\_INVALIDCAST o E\_NOINTERFACE**|**InvalidCastException**|  
|**COR\_E\_INVALIDCOMOBJECT**|**InvalidComObjectException**|  
|**COR\_E\_INVALIDFILTERCRITERIA**|**InvalidFilterCriteriaException**|  
|**COR\_E\_INVALIDOLEVARIANTTYPE**|**InvalidOleVariantTypeException**|  
|**COR\_E\_INVALIDOPERATION**|**InvalidOperationException**|  
|**COR\_E\_IO**|**IOException**|  
|**COR\_E\_MEMBERACCESS**|**AccessException**|  
|**COR\_E\_METHODACCESS**|**MethodAccessException**|  
|**COR\_E\_MISSINGFIELD**|**MissingFieldException**|  
|**COR\_E\_MISSINGMANIFESTRESOURCE**|**MissingManifestResourceException**|  
|**COR\_E\_MISSINGMEMBER**|**MissingMemberException**|  
|**COR\_E\_MISSINGMETHOD**|**MissingMethodException**|  
|**COR\_E\_MULTICASTNOTSUPPORTED**|**MulticastNotSupportedException**|  
|**COR\_E\_NOTFINITENUMBER**|**NotFiniteNumberException**|  
|**E\_NOTIMPL**|**NotImplementedException**|  
|**COR\_E\_NOTSUPPORTED**|**NotSupportedException**|  
|**COR\_E\_NULLREFERENCE o E\_POINTER**|**NullReferenceException**|  
|**COR\_E\_OUTOFMEMORY o**<br /><br /> **E\_OUTOFMEMORY**|**OutOfMemoryException**|  
|**COR\_E\_OVERFLOW**|**OverflowException**|  
|**COR\_E\_PATHTOOLONG o ERROR\_FILENAME\_EXCED\_RANGE**|**PathTooLongException**|  
|**COR\_E\_RANK**|**RankException**|  
|**COR\_E\_REFLECTIONTYPELOAD**|**ReflectionTypeLoadException**|  
|**COR\_E\_REMOTING**|**RemotingException**|  
|**COR\_E\_SAFEARRAYTYPEMISMATCH**|**SafeArrayTypeMismatchException**|  
|**COR\_E\_SECURITY**|**SecurityException**|  
|**COR\_E\_SERIALIZATION**|**SerializationException**|  
|**COR\_E\_STACKOVERFLOW o ERROR\_STACK\_OVERFLOW**|**StackOverflowException**|  
|**COR\_E\_SYNCHRONIZATIONLOCK**|**SynchronizationLockException**|  
|**COR\_E\_SYSTEM**|**SystemException**|  
|**COR\_E\_TARGET**|**TargetException**|  
|**COR\_E\_TARGETINVOCATION**|**TargetInvocationException**|  
|**COR\_E\_TARGETPARAMCOUNT**|**TargetParameterCountException**|  
|**COR\_E\_THREADABORTED**|**ThreadAbortException**|  
|**COR\_E\_THREADINTERRUPTED**|**ThreadInterruptedException**|  
|**COR\_E\_THREADSTATE**|**ThreadStateException**|  
|**COR\_E\_THREADSTOP**|**ThreadStopException**|  
|**COR\_E\_TYPELOAD**|**TypeLoadException**|  
|**COR\_E\_TYPEINITIALIZATION**|**TypeInitializationException**|  
|**COR\_E\_VERIFICATION**|**VerificationException**|  
|**COR\_E\_WEAKREFERENCE**|**WeakReferenceException**|  
|**COR\_E\_VTABLECALLSNOTSUPPORTED**|**VTableCallsNotSupportedException**|  
|**Cualquier otro resultado HRESULT**|**COMException**|  
  
 Para recuperar información de errores extendida, el cliente administrado debe examinar los campos del objeto de excepción generado.  Para que el objeto de excepción proporcione información útil acerca del error, el objeto COM debe implementar la interfaz **IErrorInfo**.  El motor de tiempo de ejecución usa la información que proporciona **IErrorInfo** para inicializar el objeto de excepción.  
  
 Si el objeto COM no es compatible con **IErrorInfo**, el motor de tiempo de ejecución inicializa un objeto de excepción con los valores predeterminados.  En la tabla siguiente se enumera cada uno de los campos asociados a un objeto de excepción y se identifica el origen de la información predeterminada cuando el objeto COM es compatible con **IErrorInfo**.  
  
 Observe que el motor en tiempo de ejecución a veces omitirá `HRESULT` en los casos en los que exista `IErrorInfo` en el subproceso.  Este comportamiento se puede producir en los casos en los que `HRESULT` y `IErrorInfo` no representen el mismo error.   ``  
  
|Campo de excepción|Origen de la información de COM|  
|------------------------|-------------------------------------|  
|**ErrorCode**|Resultado HRESULT devuelto de la llamada.|  
|**HelpLink**|Si **IErrorInfo\-\>HelpContext** no es cero, la cadena se forma concatenando **IErrorInfo\-\>GetHelpFile** y "\#" e **IErrorInfo\-\>GetHelpContext**.  En caso contrario, la cadena devuelta procede de **IErrorInfo\-\>GetHelpFile**.|  
|**InnerException**|Es siempre una referencia null \(**Nothing** en Visual Basic\).|  
|**Mensaje**|Cadena devuelta de **IErrorInfo\-\>GetDescription**.|  
|**Origen**|Cadena devuelta de **IErrorInfo\-\>GetSource**.|  
|**StackTrace**|Seguimiento de la pila.|  
|**TargetSite**|Nombre del método devuelto por el resultado HRESULT con el error.|  
  
 Los campos de excepción tales como **Message**, **Source** y **StackTrace** no están disponibles para **StackOverflowException**.  
  
## Vea también  
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Excepciones](../../../docs/standard/exceptions/index.md)