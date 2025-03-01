cmake_minimum_required(VERSION 3.12)
project(myapp)

# FetchContent モジュールのインクルード
include(FetchContent)

# mylibrary を FetchContent で追加
FetchContent_Declare(
    mylibrary
    GIT_REPOSITORY https://github.com/Asapi1020/cpp-tutorials.git
    GIT_TAG main  # バージョン指定（ここでは main ブランチ）
)

# mylibrary をプロジェクトに組み込む
FetchContent_MakeAvailable(mylibrary)

# プロジェクトのターゲットを定義
add_executable(myapp src/main.cpp)

# mylibrary をリンク
target_link_libraries(myapp PRIVATE mylibrary)

# mylibrary のヘッダーファイルの場所を追加
target_include_directories(myapp PRIVATE 
    ${mylibrary_SOURCE_DIR}/conan-publish-tutorial
)

# mylibrary.lib の場所をリンクパスに追加
target_link_directories(myapp PRIVATE ${mylibrary_BINARY_DIR}/Debug)
