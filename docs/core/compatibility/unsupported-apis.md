---
title: API no admitidas en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga información sobre qué API de .NET siempre inician una excepción en .NET Core y .NET 5 y versiones posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: b0dc425bf5f7d8f2a44f51ffe75ffcb0c8a5a7ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256262"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a>API que siempre inician excepciones en .NET Core y .NET 5+

Las API siguientes siempre iniciarán una excepción <xref:System.PlatformNotSupportedException> en .NET 5 y versiones posteriores (incluidas todas las versiones de .NET Core) en todas las plataformas, o bien en un subconjunto de estas.

En este artículo, las API afectadas se organizan por espacio de nombres.

> [!NOTE]
>
> - Este artículo sigue en desarrollo. No es una lista completa de las API que inician excepciones en .NET 5+.
> - En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que inician excepciones en .NET 5+. Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).

## <a name="system"></a>Sistema

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | All |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | Todas |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Todas |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | All |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | All |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | All |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Todas |

## <a name="systemcodedomcompiler"></a>System.CodeDom.Compiler

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | All |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | All |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | Todas |

## <a name="systemcollectionsspecialized"></a>System.Collections.Specialized

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | Todas |

## <a name="systemconfiguration"></a>System.Configuration

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros) | Todas |

## <a name="systemconsole"></a>System.Console

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener) | Linux y macOS |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener) | Linux y macOS |
| <xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |

## <a name="systemdatacommon"></a>System.Data.Common

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>) | Todas |

## <a name="systemdiagnosticsprocess"></a>System.Diagnostics.Process

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer) | Linux |
| <xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer) | Linux |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | macOS |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener) | macOS |
| <xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |

## <a name="systemio"></a>System.IO

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Todas |

## <a name="systemiopipes"></a>System.IO.Pipes

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer) | Linux y macOS |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | Linux y macOS |

## <a name="systemmedia"></a>System.Media

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Todas |

## <a name="systemnet"></a>System.Net

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | All |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | All |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | All |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | All |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Todas |

## <a name="systemnetnetworkinformation"></a>System.Net.NetworkInformation

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | Windows (UWP) |

## <a name="systemnetsockets"></a>System.Net.Sockets

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | All |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | Todas |

## <a name="systemnetwebsockets"></a>System.Net.WebSockets

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | Todas |

## <a name="systemreflection"></a>System.Reflection

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | All |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | All |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | All |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | All |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | Todas |

## <a name="systemruntimecompilerservices"></a>System.Runtime.CompilerServices

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | Todas |

## <a name="systemruntimeinteropservices"></a>System.Runtime.InteropServices

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | All |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | All |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | All |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | Todas |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | Linux y macOS |

## <a name="systemruntimeserialization"></a>System.Runtime.Serialization

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | Todas |

## <a name="systemsecurity"></a>System.Security

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | All |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | All |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | All |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | All |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | All |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | Todas |

## <a name="systemsecurityclaims"></a>System.Security.Claims

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | All |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Todas |

## <a name="systemsecuritycryptography"></a>System.Security.Cryptography

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Todas |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | Todas |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | Todas |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | Linux y macOS |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | Todas |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | Todas |

## <a name="systemsecuritycryptographypkcs"></a>System.Security.Cryptography.Pkcs

| Member | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | All |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | Todas |

## <a name="systemsecuritycryptographyx509certificates"></a>System.Security.Cryptography.X509Certificates

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | All |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | All |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Todas |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer) | Todos |

## <a name="systemsecurityauthenticationextendedprotection"></a>System.Security.Authentication.ExtendedProtection

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Todos |

## <a name="systemsecuritypolicy"></a>System.Security.Policy

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | Todos |

## <a name="systemserviceprocessservicecontroller"></a>System.ServiceProcess.ServiceController

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | Todos |

## <a name="systemtextregularexpressions"></a>System.Text.RegularExpressions

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | Todos |

## <a name="systemthreading"></a>System.Threading

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | All |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | All |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | All |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | All |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | Todas |

## <a name="systemxml"></a>System.Xml

| Miembro | Plataformas en las que se produce |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | All |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | All |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | Todas |

## <a name="see-also"></a>Vea también

- [Cambios importantes para la migración desde .NET Framework a .NET Core](fx-core.md)
- [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core)
- [Analizador de portabilidad de .NET](../../standard/analyzers/portability-analyzer.md)
