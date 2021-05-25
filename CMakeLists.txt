� ��cmake_minimum_required(VERSION 2.8)
#Проверка версии CMake.
    set(PROJECT_NAME TQueueLib)
#Создаем обычную локальную переменную с именем проекта
    project($
	    {
	    PROJECT_NAME}

)
#Название проекта
#Переменная с именем библиотеки
    set(main main)
    set(List List)
    set(QueueLib QueueLib)
    set(CMAKE_CONFIGURATION_TYPES "Debug;Release" CACHE STRING "Configs"
	FORCE)
#Создается переменная CMAKE_CONFIGURATION_TYPES со значением "Debug;Release" и меткой/разделом Configs, переменная сохраниется в специальном файле доступном из всех файлов,
    if (NOT CMAKE_BUILD_TYPE)
#проверка имеющихся у компилятора вариантов сборки
    set(CMAKE_BUILD_TYPE Release)
#Если нет то устанавливаем Release
	endif()
	include_directories($
			    {
			    CMAKE_CURRENT_SOURCE_DIR}
			    /List $ {
			    CMAKE_CURRENT_SOURCE_DIR}

			    /QueueLib)
#${CMAKE_CURRENT_SOURCE_DIR}/gtest)
#${CMAKE_CURRENT_SOURCE_DIR} - стандартная переменная с адресом рабочей директории
#Добавляем директорию с под-CMakeList-ом, и выполняем под-CMakeList
    add_subdirectory(main)
    add_subdirectory(List)
    add_subdirectory(QueueLib)
    add_subdirectory(gtest)
    add_subdirectory(test)
