# cpp-tutorials-v2
The 2nd repository of cpp tutorials for me

## CMake FetchContent
1. ライブラリをビルドできるリポジトリを用意する (https://github.com/Asapi1020/cpp-tutorials)
2. CMakeLists.txtでリポジトリとブランチを指定し、ライブラリを取り込む `cmake -B build`
3. ビルドする `cmake --build Build`

課題：利用側の負担が大きい。publish側の工夫でこれを改善したい
