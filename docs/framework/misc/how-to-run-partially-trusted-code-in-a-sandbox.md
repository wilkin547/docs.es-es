---
title: 'Cómo: Ejecutar código de confianza parcial en un recinto'
description: Descubra cómo ejecutar código de confianza parcial en un espacio aislado en .NET. La clase AppDomain es una manera eficaz de recintos de las aplicaciones administradas.
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: e02b5d679fb1f5947373399ac1226732623ef96d
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309240"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a>Cómo: Ejecutar código de confianza parcial en un recinto
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 El uso de espacios aislados consiste en ejecutar código en un entorno de seguridad restringido que limita los permisos de acceso concedidos al código. Por ejemplo, si tiene una biblioteca administrada procedente de un origen en el que no confía plenamente, no la ejecute como si fuese de plena confianza. En su lugar, coloque el código en un espacio aislado que limite los permisos a los que considere necesarios (por ejemplo, el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).  
  
 También puede usar el espacio aislado para probar el código que va a distribuir y que se ejecutará en entornos de confianza parcial.  
  
 <xref:System.AppDomain> es una forma eficaz de proporcionar un espacio aislado para las aplicaciones administradas. Los dominios de aplicación que se usan para ejecutar código de confianza parcial tienen permisos que definen los recursos protegidos que están disponibles cuando se ejecuta dentro de ese <xref:System.AppDomain>. El código que se ejecuta dentro de <xref:System.AppDomain> está limitado por los permisos asociados a <xref:System.AppDomain> y tan solo puede tener acceso a los recursos especificados. <xref:System.AppDomain> también incluye una matriz <xref:System.Security.Policy.StrongName> que se usa para identificar los ensamblados que cargan con plena confianza. Esto permite que el creador de un <xref:System.AppDomain> inicie un nuevo dominio en espacio aislado que permita confiar plenamente en ensamblados del asistente concretos. Otra opción para cargar ensamblados como de plena confianza es colocarlos en la caché de ensamblados global. Sin embargo, eso cargará los ensamblados con plena confianza en todos los dominios de aplicación creados en ese equipo. La lista de nombres seguros admite una decisión por <xref:System.AppDomain> que proporciona una determinación más restrictiva.  
  
 La sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> se puede usar para especificar el conjunto de permisos para las aplicaciones que se ejecutan en un espacio aislado. Esta sobrecarga permite especificar el nivel exacto de seguridad de acceso del código que se desea. Los ensamblados que se cargan en <xref:System.AppDomain> mediante esta sobrecarga pueden tener únicamente el conjunto de permisos especificado o pueden ser de plena confianza. Si el ensamblado está en la caché global de ensamblados o aparece enumerado en el parámetro de matrices `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>), se le concede confianza plena. Tan solo deben agregarse a la lista `fullTrustAssemblies` los ensamblados que se sabe que son de plena confianza.  
  
 La sobrecarga tiene la siguiente firma:  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 Los parámetros de la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> especifican el nombre de <xref:System.AppDomain>, la evidencia de <xref:System.AppDomain>, el objeto <xref:System.AppDomainSetup> que identifica la base de la aplicación para el espacio aislado, el conjunto de permisos que se va a usar y los nombres seguros para los ensamblados de plena confianza.  
  
 Por motivos de seguridad, la base de la aplicación especificada en el parámetro `info` no debe ser la base de la aplicación host.  
  
 Para el parámetro `grantSet`, puede especificar un conjunto de permisos que haya creado explícitamente o un conjunto de permisos estándar conjunto creado mediante el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A>.  
  
 A diferencia de la mayoría de cargas de <xref:System.AppDomain>, la evidencia para <xref:System.AppDomain> (proporcionado por el parámetro `securityInfo`) no se usa para determinar el conjunto de permisos de los ensamblados de confianza parcial. En su lugar, se especifica por separado mediante el parámetro `grantSet`. Sin embargo, la evidencia puede usarse para otros fines como determinar el ámbito de almacenamiento aislado.  
  
### <a name="to-run-an-application-in-a-sandbox"></a>Para ejecutar una aplicación en un espacio aislado  
  
1. Cree el conjunto de permisos que se concederán a la aplicación no confiable. El permiso mínimo que se puede conceder es <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>. También puede conceder permisos adicionales si piensa que son seguros para el código no seguro, por ejemplo, <xref:System.Security.Permissions.IsolatedStorageFilePermission>. El siguiente código crea un nuevo conjunto de permisos que contiene únicamente el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     Si lo prefiere, puede usar un conjunto de permisos con nombre existente, como Internet.  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     El método <xref:System.Security.SecurityManager.GetStandardSandbox%2A> devolverá un conjunto de permisos `Internet` o un conjunto de permisos `LocalIntranet` según la zona de la evidencia. <xref:System.Security.SecurityManager.GetStandardSandbox%2A> también construye permisos de identidad para algunos de los objetos de evidencia que se pasan como referencias.  
  
2. Firme el ensamblado que contiene la clase host (denominada `Sandboxer` en este ejemplo) que llama al código de confianza. Agregue el <xref:System.Security.Policy.StrongName> usado para firmar el ensamblado a la matriz <xref:System.Security.Policy.StrongName> del parámetro `fullTrustAssemblies` de la llamada <xref:System.AppDomain.CreateDomain%2A>. La clase host debe ejecutarse como de plena confianza para habilitar la ejecución del código de confianza parcial u ofrecer servicios a la aplicación de confianza parcial. Así es como se lee el <xref:System.Security.Policy.StrongName> de un ensamblado:  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     Los ensamblados de .NET Framework como mscorlib y System.dll no tienen que agregarse a la lista de plena confianza porque se cargan como de plena confianza desde la caché de ensamblados global.  
  
3. Inicialice el parámetro <xref:System.AppDomainSetup> del método <xref:System.AppDomain.CreateDomain%2A>. Con este parámetro, puede controlar muchas de las opciones del nuevo <xref:System.AppDomain>. La propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> es un valor importante y debe ser diferente de la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> para el <xref:System.AppDomain> de la aplicación host. Si los valores de <xref:System.AppDomainSetup.ApplicationBase%2A> son iguales, la aplicación de confianza parcial puede hacer que la aplicación host cargue (como de plena confianza) una excepción que define y, por tanto, aprovecharse de ella. Este es otro motivo por el que no se recomienda un bloque catch (excepción). El riesgo de ataques se reduce si la base de la aplicación del host y la base de la aplicación de la aplicación en espacio aislado se configuran de forma diferente.  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. Llame a la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> para crear el dominio de aplicación usando los parámetros especificados.  
  
     La firma de este método es:  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     Información adicional:  
  
    - Esta es la única sobrecarga del método <xref:System.AppDomain.CreateDomain%2A> que toma <xref:System.Security.PermissionSet> como un parámetro y, por lo tanto, la única sobrecarga que permite cargar una aplicación en un entorno de confianza parcial.  
  
    - El parámetro `evidence` no se usa para calcular un conjunto de permisos, sino que se usa para identificar otras características de .NET Framework.  
  
    - En esta sobrecarga es obligatorio establecer la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> del parámetro `info`.  
  
    - El parámetro `fullTrustAssemblies` tiene la palabra clave `params`, lo que significa que no es necesario crear una matriz <xref:System.Security.Policy.StrongName>. Se permite pasar 0, 1 o más nombres seguros como parámetros.  
  
    - El código para crear el dominio de aplicación es:  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. Cargar el código en el espacio aislado <xref:System.AppDomain> que creó. Esto puede hacerse de dos maneras:  
  
    - Llame al método <xref:System.AppDomain.ExecuteAssembly%2A> para el ensamblado.  
  
    - Use el método <xref:System.Activator.CreateInstanceFrom%2A> para crear una instancia de una clase derivada de <xref:System.MarshalByRefObject> en el nuevo <xref:System.AppDomain>.  
  
     El segundo método es preferible, porque es más fácil pasar parámetros a la nueva instancia <xref:System.AppDomain>. El método <xref:System.Activator.CreateInstanceFrom%2A> proporciona dos características importantes:  
  
    - Puede usar una base de código que apunte a una ubicación que no contenga su ensamblado.  
  
    - Puede realizar la creación en un <xref:System.Security.CodeAccessPermission.Assert%2A> de plena confianza (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), lo que le permite crear una instancia de una clase crítica. (Esto sucede cuando el ensamblado no tiene marcas de transparencia y se carga como de plena confianza). Por lo tanto, debe tener cuidado de crear solo código en el que confíe con esta función y se recomienda crear solo instancias de clases de plena confianza en el nuevo dominio de aplicación.  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     Para crear una instancia de una clase en un dominio nuevo, la clase debe extender la <xref:System.MarshalByRefObject> clase.
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. Desempaquete la nueva instancia del dominio en una referencia en este dominio. Esta referencia se usa para ejecutar el código no confiable.  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. Llame al método `ExecuteUntrustedCode` en la instancia de la clase `Sandboxer` que acaba de crear.  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     Esta llamada se ejecuta en el dominio de la aplicación en espacio aislado, que tiene permisos restringidos.  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <xref:System.Reflection> se usa para obtener el identificador de un método en el ensamblado de confianza parcial. El identificador puede usarse para ejecutar código de forma segura con permisos mínimos.  
  
     En el código anterior, observe <xref:System.Security.PermissionSet.Assert%2A> para el permiso de plena confianza antes de imprimir <xref:System.Security.SecurityException>.  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     La aserción de plena confianza se usa para obtener la información ampliada de <xref:System.Security.SecurityException>. Sin <xref:System.Security.PermissionSet.Assert%2A>, el método <xref:System.Security.SecurityException.ToString%2A> de <xref:System.Security.SecurityException> detectará que hay código de confianza parcial en la pila y restringirá la información devuelta. Esto podría provocar problemas de seguridad si el código de confianza parcial llega a leer esa información, pero el riesgo se mitiga al no conceder <xref:System.Security.Permissions.UIPermission>. La aserción de plena confianza debe usarse con moderación y solo cuando si se está seguro de que no se permite al código de confianza parcial elevarse a plena confianza. Como norma general, no llame a un código en el que no confía en la misma función y tras invocar una aserción de plena confianza. Le recomendamos que revierta siempre la aserción cuando acabe de usarla.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se implementa el procedimiento de la sección anterior. En el ejemplo, un proyecto denominado `Sandboxer` en una solución de Visual Studio también contiene un proyecto denominado `UntrustedCode` que implementa la clase `UntrustedClass`. En este escenario se supone que ha descargado un ensamblado de biblioteca que contiene un método que debe devolver `true` o `false` para indicar si el número proporcionado es un número de Fibonacci. En su lugar, el método intenta leer un archivo de su equipo. En el ejemplo siguiente se muestra el código no confiable.  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 En el ejemplo siguiente se muestra el código de la aplicación `Sandboxer` que ejecuta el código no confiable.  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Consulte también

- [Instrucciones de codificación segura](../../standard/security/secure-coding-guidelines.md)
