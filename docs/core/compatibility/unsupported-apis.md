---
title: API no admitidas en .NET Core y .NET 5+
titleSuffix: ''
description: Obtenga información sobre qué API de .NET siempre inician una excepción en .NET Core y .NET 5.0 y versiones posteriores.
ms.date: 10/13/2020
ms.openlocfilehash: 1bd41192d0d6752d2b659da9fb6387dac321b2c3
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593271"
---
# <a name="apis-that-always-throw-exceptions-on-net-core-and-net-5"></a><span data-ttu-id="97b54-103">API que siempre inician excepciones en .NET Core y .NET 5+</span><span class="sxs-lookup"><span data-stu-id="97b54-103">APIs that always throw exceptions on .NET Core and .NET 5+</span></span>

<span data-ttu-id="97b54-104">Las API siguientes siempre iniciarán una excepción <xref:System.PlatformNotSupportedException> en .NET 5.0 y versiones posteriores (incluidas todas las versiones de .NET Core) en todas las plataformas, o bien en un subconjunto de estas.</span><span class="sxs-lookup"><span data-stu-id="97b54-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET 5.0 and later versions (including all versions of .NET Core) on all or a subset of platforms.</span></span>

<span data-ttu-id="97b54-105">En este artículo, las API afectadas se organizan por espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="97b54-105">This article organizes the affected APIs by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="97b54-106">Este artículo sigue en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="97b54-106">This article is a work-in-progress.</span></span> <span data-ttu-id="97b54-107">No es una lista completa de las API que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="97b54-107">It is not a complete list of APIs that throw exceptions on .NET 5+.</span></span>
> - <span data-ttu-id="97b54-108">En este artículo no se incluyen las implementaciones de interfaz explícitas para la serialización binaria que inician excepciones en .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="97b54-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET 5+.</span></span> <span data-ttu-id="97b54-109">Para obtener más información, vea [Serialización binaria en .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="97b54-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="97b54-110">Sistema</span><span class="sxs-lookup"><span data-stu-id="97b54-110">System</span></span>

| <span data-ttu-id="97b54-111">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-111">Member</span></span> | <span data-ttu-id="97b54-112">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-113">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="97b54-114">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="97b54-115">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="97b54-116">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-117">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="97b54-118">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="97b54-119">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="97b54-120">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-121">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="97b54-122">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="97b54-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="97b54-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="97b54-124">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-124">Member</span></span> | <span data-ttu-id="97b54-125">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-126">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-127">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-128">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="97b54-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="97b54-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="97b54-130">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-130">Member</span></span> | <span data-ttu-id="97b54-131">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-132">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-133">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="97b54-134">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="97b54-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="97b54-135">System.Configuration</span></span>

| <span data-ttu-id="97b54-136">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-136">Member</span></span> | <span data-ttu-id="97b54-137">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="97b54-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (todos los miembros)</span><span class="sxs-lookup"><span data-stu-id="97b54-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="97b54-139">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="97b54-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="97b54-140">System.Console</span></span>

| <span data-ttu-id="97b54-141">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-141">Member</span></span> | <span data-ttu-id="97b54-142">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="97b54-143">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-143">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-145">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-145">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-147">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-147">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-149">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-149">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="97b54-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="97b54-151">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-152">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-153">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-154">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-154">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-155"><xref:System.Console.Title?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="97b54-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="97b54-156">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-156">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-158">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-158">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-160">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-160">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-162">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-162">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-164">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="97b54-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="97b54-165">System.Data.Common</span></span>

| <span data-ttu-id="97b54-166">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-166">Member</span></span> | <span data-ttu-id="97b54-167">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="97b54-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (genera <xref:System.NotSupportedException>)</span><span class="sxs-lookup"><span data-stu-id="97b54-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="97b54-169">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="97b54-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="97b54-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="97b54-171">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-171">Member</span></span> | <span data-ttu-id="97b54-172">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="97b54-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-174">Linux</span><span class="sxs-lookup"><span data-stu-id="97b54-174">Linux</span></span> |
| <span data-ttu-id="97b54-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-176">Linux</span><span class="sxs-lookup"><span data-stu-id="97b54-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="97b54-177">macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="97b54-178">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-179">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start(System.String,System.String,System.Security.SecureString,System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-180">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="97b54-181">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="97b54-182">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="97b54-183">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-183">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="97b54-184">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-184">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-185"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-186">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-186">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (solo Obtener)</span><span class="sxs-lookup"><span data-stu-id="97b54-187"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="97b54-188">macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-188">macOS</span></span> |
| <span data-ttu-id="97b54-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-189"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-190">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-190">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="97b54-191">System.IO</span><span class="sxs-lookup"><span data-stu-id="97b54-191">System.IO</span></span>

| <span data-ttu-id="97b54-192">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-192">Member</span></span> | <span data-ttu-id="97b54-193">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-193">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-194">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-194">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-195">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-195">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="97b54-196">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="97b54-196">System.IO.Pipes</span></span>

| <span data-ttu-id="97b54-197">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-197">Member</span></span> | <span data-ttu-id="97b54-198">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-198">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="97b54-199">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="97b54-200">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="97b54-201">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-201">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="97b54-202">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-202">Linux and macOS</span></span> |
| <span data-ttu-id="97b54-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-203"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-204">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-204">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="97b54-205">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-205">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="97b54-206">System.Media</span><span class="sxs-lookup"><span data-stu-id="97b54-206">System.Media</span></span>

| <span data-ttu-id="97b54-207">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-207">Member</span></span> | <span data-ttu-id="97b54-208">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-208">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-209">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-209">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="97b54-210">System.Net</span><span class="sxs-lookup"><span data-stu-id="97b54-210">System.Net</span></span>

| <span data-ttu-id="97b54-211">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-211">Member</span></span> | <span data-ttu-id="97b54-212">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-212">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="97b54-213">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-213">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="97b54-214">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-214">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-215">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-215">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-216">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-216">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-217">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-217">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-218">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-219">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-219">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-220">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-221">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-221">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-222">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-222">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-223">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-223">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="97b54-224">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-224">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-225">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-225">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-226">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-226">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-227">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-227">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-228">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-228">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-229">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-229">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="97b54-230">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="97b54-230">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="97b54-231">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-231">Member</span></span> | <span data-ttu-id="97b54-232">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-232">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-233">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="97b54-233">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="97b54-234">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="97b54-234">System.Net.Sockets</span></span>

| <span data-ttu-id="97b54-235">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-235">Member</span></span> | <span data-ttu-id="97b54-236">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-236">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="97b54-237">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-237">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="97b54-238">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-238">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="97b54-239">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="97b54-239">System.Net.WebSockets</span></span>

| <span data-ttu-id="97b54-240">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-240">Member</span></span> | <span data-ttu-id="97b54-241">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-241">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="97b54-242">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-242">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="97b54-243">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="97b54-243">System.Reflection</span></span>

| <span data-ttu-id="97b54-244">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-244">Member</span></span> | <span data-ttu-id="97b54-245">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-245">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-246">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-246">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-247">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-248">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-248">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="97b54-249">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="97b54-250">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-251">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-251">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="97b54-252">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-252">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="97b54-253">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="97b54-253">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="97b54-254">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-254">Member</span></span> | <span data-ttu-id="97b54-255">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-255">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="97b54-256">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-256">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="97b54-257">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="97b54-257">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="97b54-258">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-258">Member</span></span> | <span data-ttu-id="97b54-259">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-259">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="97b54-260">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="97b54-261">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="97b54-262">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-262">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="97b54-263">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-263">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-264">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="97b54-265">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-265">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="97b54-266">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-266">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="97b54-267">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="97b54-267">System.Runtime.Serialization</span></span>

| <span data-ttu-id="97b54-268">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-268">Member</span></span> | <span data-ttu-id="97b54-269">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-269">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="97b54-270">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-270">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="97b54-271">System.Security</span><span class="sxs-lookup"><span data-stu-id="97b54-271">System.Security</span></span>

| <span data-ttu-id="97b54-272">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-272">Member</span></span> | <span data-ttu-id="97b54-273">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-273">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="97b54-274">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-274">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="97b54-275">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-275">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-276">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-276">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="97b54-277">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-277">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="97b54-278">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-278">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="97b54-279">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-279">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="97b54-280">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-280">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="97b54-281">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="97b54-282">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-282">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="97b54-283">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-283">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="97b54-284">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-284">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="97b54-285">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="97b54-286">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-286">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="97b54-287">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-287">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="97b54-288">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="97b54-288">System.Security.Claims</span></span>

| <span data-ttu-id="97b54-289">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-289">Member</span></span> | <span data-ttu-id="97b54-290">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-290">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-291">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-292">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="97b54-293">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-294">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-294">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-295">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-295">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="97b54-296">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="97b54-296">System.Security.Cryptography</span></span>

| <span data-ttu-id="97b54-297">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-297">Member</span></span> | <span data-ttu-id="97b54-298">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-298">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-299">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-299">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="97b54-300">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="97b54-301">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="97b54-302">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="97b54-303">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="97b54-304">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="97b54-305">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="97b54-306">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="97b54-307">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="97b54-308">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="97b54-309">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="97b54-310">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="97b54-311">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="97b54-312">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-312">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="97b54-313">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="97b54-314">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-315">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-316">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-317">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-317">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-318">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="97b54-319">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-319">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-320">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-320">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-321">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-322">Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="97b54-322">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-323">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-323">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-324">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="97b54-325">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-325">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="97b54-326">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-326">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="97b54-327">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="97b54-327">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="97b54-328">Member</span><span class="sxs-lookup"><span data-stu-id="97b54-328">Member</span></span> | <span data-ttu-id="97b54-329">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-329">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="97b54-330">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="97b54-331">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="97b54-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="97b54-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="97b54-333">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-333">Member</span></span> | <span data-ttu-id="97b54-334">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-335">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-336">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-337">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-337">All</span></span> |
| <span data-ttu-id="97b54-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (solo Establecer)</span><span class="sxs-lookup"><span data-stu-id="97b54-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="97b54-339">Todos</span><span class="sxs-lookup"><span data-stu-id="97b54-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="97b54-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="97b54-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="97b54-341">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-341">Member</span></span> | <span data-ttu-id="97b54-342">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-343">Todos</span><span class="sxs-lookup"><span data-stu-id="97b54-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="97b54-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="97b54-344">System.Security.Policy</span></span>

| <span data-ttu-id="97b54-345">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-345">Member</span></span> | <span data-ttu-id="97b54-346">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-347">Todos</span><span class="sxs-lookup"><span data-stu-id="97b54-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="97b54-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="97b54-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="97b54-349">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-349">Member</span></span> | <span data-ttu-id="97b54-350">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="97b54-351">Todos</span><span class="sxs-lookup"><span data-stu-id="97b54-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="97b54-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="97b54-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="97b54-353">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-353">Member</span></span> | <span data-ttu-id="97b54-354">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-355">Todos</span><span class="sxs-lookup"><span data-stu-id="97b54-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="97b54-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="97b54-356">System.Threading</span></span>

| <span data-ttu-id="97b54-357">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-357">Member</span></span> | <span data-ttu-id="97b54-358">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-359">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="97b54-360">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="97b54-361">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="97b54-362">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="97b54-363">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="97b54-364">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="97b54-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="97b54-365">System.Xml</span></span>

| <span data-ttu-id="97b54-366">Miembro</span><span class="sxs-lookup"><span data-stu-id="97b54-366">Member</span></span> | <span data-ttu-id="97b54-367">Plataformas en las que se produce</span><span class="sxs-lookup"><span data-stu-id="97b54-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="97b54-368">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="97b54-369">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="97b54-370">Todas</span><span class="sxs-lookup"><span data-stu-id="97b54-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="97b54-371">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b54-371">See also</span></span>

- [<span data-ttu-id="97b54-372">Cambios importantes para la migración desde .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="97b54-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](fx-core.md)
- [<span data-ttu-id="97b54-373">Serialización binaria en .NET Core</span><span class="sxs-lookup"><span data-stu-id="97b54-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="97b54-374">Analizador de portabilidad de .NET</span><span class="sxs-lookup"><span data-stu-id="97b54-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
