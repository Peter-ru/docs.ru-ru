---
title: "Сборка .NET Core из исходного кода"
description: "Узнайте, как выполнять сборку .NET Core и интерфейса командной строки .NET Core из исходного кода."
keywords: ".NET, .NET Core, исходный код, сборка"
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8b49079c-6ede-429a-92d7-ecd2fda1ab0e
ms.openlocfilehash: b2e62074992432dc5ee1360e17f87c782685dc35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="75717-104">Сборка .NET Core из исходного кода</span><span class="sxs-lookup"><span data-stu-id="75717-104">Build .NET Core from source</span></span>

<span data-ttu-id="75717-105">Возможность сборки .NET Core из своего исходного кода важна по многим причинам: это упрощает перенос кода .NET Core на новые платформы, позволяет вносить в продукт дополнения и исправления, а также создавать пользовательские версии .NET.</span><span class="sxs-lookup"><span data-stu-id="75717-105">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="75717-106">В статье представлены рекомендации для разработчиков, которые хотят осуществлять сборку и распространение собственных версий .NET Core.</span><span class="sxs-lookup"><span data-stu-id="75717-106">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="75717-107">Сборка среды CLR из исходного кода</span><span class="sxs-lookup"><span data-stu-id="75717-107">Build the CLR from source</span></span>

<span data-ttu-id="75717-108">Исходный код .NET CoreCLR можно найти в [репозитории GitHub `dotnet/coreclr`](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="75717-108">The source code for the .NET CoreCLR can be found in [the `dotnet/coreclr` repository on GitHub](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="75717-109">Для сборки сейчас необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="75717-109">The build currently depends on the following prerequisites:</span></span>
* [<span data-ttu-id="75717-110">Git</span><span class="sxs-lookup"><span data-stu-id="75717-110">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="75717-111">CMake</span><span class="sxs-lookup"><span data-stu-id="75717-111">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="75717-112">Python</span><span class="sxs-lookup"><span data-stu-id="75717-112">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="75717-113">Компилятор C++</span><span class="sxs-lookup"><span data-stu-id="75717-113">a C++ compiler.</span></span>

<span data-ttu-id="75717-114">После установки необходимых компонентов вы можете собрать CLR, запустив сценарий (`build.cmd` в Windows или `build.sh` в Linux и macOS) из корня [репозитория Core CLR](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="75717-114">After you've installed these prerequisites are installed, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of [the CoreCLR repository](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="75717-115">Устанавливаемые компоненты отличаются в зависимости от операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="75717-115">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="75717-116">Инструкции по сборке для конкретных ОС:</span><span class="sxs-lookup"><span data-stu-id="75717-116">See the build instructions for your specific OS:</span></span>

 * [<span data-ttu-id="75717-117">Windows</span><span class="sxs-lookup"><span data-stu-id="75717-117">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
 * [<span data-ttu-id="75717-118">Linux</span><span class="sxs-lookup"><span data-stu-id="75717-118">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
 * [<span data-ttu-id="75717-119">macOS</span><span class="sxs-lookup"><span data-stu-id="75717-119">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
 * [<span data-ttu-id="75717-120">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="75717-120">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md) 
 * [<span data-ttu-id="75717-121">NetBSD</span><span class="sxs-lookup"><span data-stu-id="75717-121">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="75717-122">Сборка из одной ОС под другие ОС не поддерживается (за исключением ARM, где сборка осуществляется на X64).</span><span class="sxs-lookup"><span data-stu-id="75717-122">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="75717-123">Сборка под конкретную платформу должна осуществляться на этой же платформе.</span><span class="sxs-lookup"><span data-stu-id="75717-123">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="75717-124">Сборка имеет два основных типа `buildTypes`:</span><span class="sxs-lookup"><span data-stu-id="75717-124">The build has two main `buildTypes`:</span></span>

 * <span data-ttu-id="75717-125">Debug — применяется по умолчанию; компилирует среду выполнения с минимальным уровнем оптимизации и использованием дополнительных проверок среды выполнения (утверждения assert).</span><span class="sxs-lookup"><span data-stu-id="75717-125">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="75717-126">Понижение уровня оптимизации и дополнительные проверки замедляют работу среды выполнения, но это необходимо делать для отладки.</span><span class="sxs-lookup"><span data-stu-id="75717-126">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="75717-127">Этот тип рекомендуется использовать со средами разработки и тестирования.</span><span class="sxs-lookup"><span data-stu-id="75717-127">This is the recommended setting for development and testing environments.</span></span>
 * <span data-ttu-id="75717-128">Release — компилирует среду выполнения с исходным уровнем оптимизации и без использования дополнительных проверок среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="75717-128">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="75717-129">Это существенно ускоряет выполнение, но сборка займет немного больше времени, а отладка будет затруднена.</span><span class="sxs-lookup"><span data-stu-id="75717-129">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="75717-130">Чтобы выбрать этот тип сборки, передайте `release` в соответствующий скрипт.</span><span class="sxs-lookup"><span data-stu-id="75717-130">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="75717-131">Кроме того, по умолчанию сборка не только создает исполняемые файлы среды выполнения, но и создает все тесты.</span><span class="sxs-lookup"><span data-stu-id="75717-131">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="75717-132">Тестов довольно много, и они занимают немало времени. Однако, если вы хотите просто поэкспериментировать с изменениями, использовать тесты не обязательно.</span><span class="sxs-lookup"><span data-stu-id="75717-132">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="75717-133">Вы можете пропустить создание тестов, добавив аргумент в сценарий сборки `skiptests`, как показано в следующем примере (замените `.\build` на `./build.sh` на компьютерах с ОС Unix):</span><span class="sxs-lookup"><span data-stu-id="75717-133">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests 
```

<span data-ttu-id="75717-134">В предыдущем примере показано, как выполнить сборку типа `Debug`со включенными проверками времени разработки (утверждения assert) и отключенной оптимизацией.</span><span class="sxs-lookup"><span data-stu-id="75717-134">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="75717-135">Чтобы создать конфигурацию Release (Выпуск), обеспечивающую максимальную скорость работы, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="75717-135">To build the release (full speed) flavor, do the following:</span></span>

```bat 
    .\build release skiptests
```

<span data-ttu-id="75717-136">Чтобы просмотреть другие варианты сборки, запустите build с квалификатором "-?"</span><span class="sxs-lookup"><span data-stu-id="75717-136">You can find more build options with build by using the -?</span></span> <span data-ttu-id="75717-137">или "-help".</span><span class="sxs-lookup"><span data-stu-id="75717-137">or -help qualifier.</span></span>   

### <a name="using-your-build"></a><span data-ttu-id="75717-138">Использование сборки</span><span class="sxs-lookup"><span data-stu-id="75717-138">Using Your Build</span></span>

<span data-ttu-id="75717-139">Сборка помещает все созданные файлы в каталог `bin` в корне репозитория.</span><span class="sxs-lookup"><span data-stu-id="75717-139">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="75717-140">Каталог *bin\Log* содержит созданные во время сборки файлы журнала (они особенно полезны при неудачной сборке).</span><span class="sxs-lookup"><span data-stu-id="75717-140">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="75717-141">Фактический результат размещается в каталоге *bin\Product\[платформа].[архитектура_процессора].[тип_сборки]*, например *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="75717-141">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="75717-142">Хотя "сырой" результат сборки иногда бывает полезен, обычно вам нужны только пакеты NuGet, которые размещаются в подкаталоге `.nuget\pkg` предыдущего выходного каталога.</span><span class="sxs-lookup"><span data-stu-id="75717-142">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="75717-143">Существует два основных метода использования новой среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="75717-143">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="75717-144">**Использование dotnet.exe и NuGet для создания приложения**.</span><span class="sxs-lookup"><span data-stu-id="75717-144">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="75717-145">Воспользуйтесь указаниями на странице [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) (Использование сборки), чтобы создать программу, использующую вашу новую среду выполнения, на основе только что созданных вами пакетов NuGet и интерфейса командной строки dotnet.</span><span class="sxs-lookup"><span data-stu-id="75717-145">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="75717-146">Разработчики, не работающие в среде выполнения, скорее всего будут взаимодействовать с вашей новой средой выполнения именно таким способом.</span><span class="sxs-lookup"><span data-stu-id="75717-146">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>    

 2. <span data-ttu-id="75717-147">**Использование corerun.exe для запуска приложения с помощью неупакованных библиотек DLL**.</span><span class="sxs-lookup"><span data-stu-id="75717-147">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="75717-148">Этот репозиторий также задает простое основное приложение corerun.exe, у которого НЕТ зависимостей в NuGet.</span><span class="sxs-lookup"><span data-stu-id="75717-148">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="75717-149">Необходимо сообщить этому приложению, где получить именно те библиотеки DLL, которые вы используете. Вам нужно будет собрать эти библиотеки вместе вручную.</span><span class="sxs-lookup"><span data-stu-id="75717-149">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="75717-150">Этот метод используется во всех тестах в [репозитории CoreCLR](https://github.com/dotnet/coreclr). Его можно использовать для быстрого локального проведения цикла "правка — компиляция — отладка", например для предварительного модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="75717-150">This technique is used by all the tests in [the CoreCLR repo](https://github.com/dotnet/coreclr), and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="75717-151">Подробнее об использовании этого метода см. в статье [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) (Запуск приложений .NET Core с помощью CoreRun.exe).</span><span class="sxs-lookup"><span data-stu-id="75717-151">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="75717-152">Сборка интерфейса командной строки из исходного кода</span><span class="sxs-lookup"><span data-stu-id="75717-152">Build the CLI from source</span></span>

<span data-ttu-id="75717-153">Исходный код для интерфейса командной строки (CLI) .NET Core находится в [GitHub-репозитории `dotnet/cli`](https://github.com/dotnet/cli/).</span><span class="sxs-lookup"><span data-stu-id="75717-153">The source code for the .NET Core CLI can be found in [the `dotnet/cli` repository on GitHub](https://github.com/dotnet/cli/).</span></span>

<span data-ttu-id="75717-154">Для сборки CLI-интерфейса .NET Core на компьютеры должны быть установлены следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="75717-154">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="75717-155">Windows и Linux:</span><span class="sxs-lookup"><span data-stu-id="75717-155">Windows & Linux:</span></span>
    - <span data-ttu-id="75717-156">git в каталоге переменной PATH</span><span class="sxs-lookup"><span data-stu-id="75717-156">git on the PATH</span></span>
* <span data-ttu-id="75717-157">macOS:</span><span class="sxs-lookup"><span data-stu-id="75717-157">macOS:</span></span>
    - <span data-ttu-id="75717-158">git в каталоге переменной PATH</span><span class="sxs-lookup"><span data-stu-id="75717-158">git on the PATH</span></span>
    - <span data-ttu-id="75717-159">Xcode</span><span class="sxs-lookup"><span data-stu-id="75717-159">Xcode</span></span>
    - <span data-ttu-id="75717-160">Openssl</span><span class="sxs-lookup"><span data-stu-id="75717-160">OpenSSL</span></span>

<span data-ttu-id="75717-161">Чтобы выполнить сборку, запустите `build.cmd` в Windows или `build.sh` в Linux и macOS из корня.</span><span class="sxs-lookup"><span data-stu-id="75717-161">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="75717-162">Если вы не хотите выполнять тесты, используйте `build.cmd /t:Compile` или `./build.sh /t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="75717-162">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="75717-163">Для сборки CLI в macOS Sierra задайте значение переменной среды DOTNET_RUNTIME_ID, выполнив `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="75717-163">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="75717-164">Использование сборки</span><span class="sxs-lookup"><span data-stu-id="75717-164">Using your build</span></span>

<span data-ttu-id="75717-165">Чтобы испытать созданный CLI-интерфейс, используйте исполняемый файл `dotnet` из *artifacts/{os}-{arch}/stage2*.</span><span class="sxs-lookup"><span data-stu-id="75717-165">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="75717-166">Если вы хотите использовать результат сборки при вызове `dotnet` из текущей консоли, вы можете также добавить *artifacts/{os}-{arch}/stage2* в переменную PATH.</span><span class="sxs-lookup"><span data-stu-id="75717-166">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="75717-167">См. также</span><span class="sxs-lookup"><span data-stu-id="75717-167">See also</span></span>

* [<span data-ttu-id="75717-168">Общеязыковая среда выполнения .NET Core (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="75717-168">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="75717-169">Руководство разработчика по интерфейсу командной строки .NET Core</span><span class="sxs-lookup"><span data-stu-id="75717-169">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="75717-170">Упаковка дистрибутивов .NET Core</span><span class="sxs-lookup"><span data-stu-id="75717-170">.NET Core distribution packaging</span></span>](./distribution-packaging.md)