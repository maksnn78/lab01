# Лабораторная работа №1
## Аксентьев Максим ИУ8-22
## 1.Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.
```bash
wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
```bash
--2026-03-22 12:16:48--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
Resolving sourceforge.net (sourceforge.net)... 2606:4700::6812:d95, 2606:4700::6812:c95, 104.18.13.149, ...
Connecting to sourceforge.net (sourceforge.net)|2606:4700::6812:d95|:443... connected.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/ [following]
--2026-03-22 12:16:48--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/
Reusing existing connection to [sourceforge.net]:443.
HTTP request sent, awaiting response... 301 Moved Permanently
Location: https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download [following]
--2026-03-22 12:16:48--  https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz/download
Reusing existing connection to [sourceforge.net]:443.
HTTP request sent, awaiting response... 302 Found
Location: https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABpv7OAulfAQ2ydQ8oeZIbM2oB10F9vPvB2Po1NABnN8Yj0Hbzjnqi_fF7Dd4_aKGYx4ulaUUBh8y23U8BtbcA3SBm6iw%3D%3D&use_mirror=sf-eu-introserv-1&r= [following]
--2026-03-22 12:16:49--  https://downloads.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?ts=gAAAAABpv7OAulfAQ2ydQ8oeZIbM2oB10F9vPvB2Po1NABnN8Yj0Hbzjnqi_fF7Dd4_aKGYx4ulaUUBh8y23U8BtbcA3SBm6iw%3D%3D&use_mirror=sf-eu-introserv-1&r=
Resolving downloads.sourceforge.net (downloads.sourceforge.net)... 2606:4700::6812:d95, 2606:4700::6812:c95, 104.18.12.149, ...
Connecting to downloads.sourceforge.net (downloads.sourceforge.net)|2606:4700::6812:d95|:443... connected.
HTTP request sent, awaiting response... 302 Found
Location: https://sf-eu-introserv-1.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1 [following]
--2026-03-22 12:16:49--  https://sf-eu-introserv-1.dl.sourceforge.net/project/boost/boost/1.69.0/boost_1_69_0.tar.gz?viasf=1
Resolving sf-eu-introserv-1.dl.sourceforge.net (sf-eu-introserv-1.dl.sourceforge.net)... 141.95.66.71
Connecting to sf-eu-introserv-1.dl.sourceforge.net (sf-eu-introserv-1.dl.sourceforge.net)|141.95.66.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 111710205 (107M) [application/x-gzip]
Saving to: ‘boost_1_69_0.tar.gz’

boost_1_69_0.tar.gz 100%[===================>] 106,53M  11,3MB/s    in 9,8s    

2026-03-22 12:17:00 (10,9 MB/s) - ‘boost_1_69_0.tar.gz’ saved [111710205/111710205]
```
## 2. Разархивируйте скаченный файл в директорию ~/boost_1_69_0.
```bash
tar -xzf boost_1_69_0.tar.gz
```
## 3. Подсчитайте количество файлов в директории ~/boost_1_69_0 не включая вложенные директории.
```bash
find boost_1_69_0 -maxdepth 1 -type f | wc -l
```
```bash
12
```
## 4. Подсчитайте количество файлов в директории ~/boost_1_69_0 включая вложенные директории.
```bash
find boost_1_69_0 -type f | wc -l
```
```bash
61191
```
## 5. Подсчитайте количество заголовочных файлов, файлов с расширением .cpp, сколько остальных файлов (не заголовочных и не .cpp).
```bash
find boost_1_69_0 -type f \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" -o -name "*.inl" \) | wc -l
```
```bash
15209
```
```bash
find boost_1_69_0 -type f -name "*.cpp" |wc -l
```
```bash
13774
```
```bash
find boost_1_69_0 -type f ! \( -name "*.h" -o -name "*.hpp" -o -name "*.hxx" -o -name "*.inl" -o -name "*.cpp" \) | wc -l
```
```bash
32208
```
## 6. Найдите полный пусть до файла any.hpp внутри библиотеки boost.
```bash
find boost_1_69_0 -name "any.hpp"
```
```bash
boost_1_69_0/boost/proto/detail/any.hpp
boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
boost_1_69_0/boost/type_erasure/any.hpp
boost_1_69_0/boost/fusion/include/any.hpp
boost_1_69_0/boost/fusion/algorithm/query/any.hpp
boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
boost_1_69_0/boost/any.hpp
boost_1_69_0/boost/hana/any.hpp
boost_1_69_0/boost/hana/fwd/any.hpp
boost_1_69_0/boost/xpressive/detail/utility/any.hpp
```
## 7. Выведите в консоль все файлы, где упоминается последовательность boost::asio.
```bash
grep -rl "boost::asio" boost_1_69_0 > asio_usage.txt
```
[asio_usage.txt](https://github.com/maksnn78/lab01/blob/master/asio_usage.txt)
## 8. Скомпилирутйе boost. Можно воспользоваться инструкцией или ссылкой.
```bash
wget https://archives.boost.io/release/1.83.0/source/boost_1_83_0.tar.gz
tar -xzf boost_1_83_0.tar.gz
cd boost_1_83_0
./bootstrap.sh
./b2 -j$(nproc) > build.log 2>&1
mv build.log ~/lab01
cd ~/lab01
git add build.log
git commit -m "boost 1.83 full build log"
git push origin master
```
[build.log](https://github.com/maksnn78/lab01/blob/master/build.log)
## 9.Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ~/boost-libs.
```bash
mkdir boost-libs
cp boost_1_69_0/stage/lib/*.a ~/boost-libs/
```
## 10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
```bash
du -h boost-libs/*
```
```bash
4,0K	boost-libs/libboost_atomic.a
236K	boost-libs/libboost_chrono.a
148K	boost-libs/libboost_container.a
24K	boost-libs/libboost_context.a
344K	boost-libs/libboost_contract.a
152K	boost-libs/libboost_date_time.a
4,0K	boost-libs/libboost_exception.a
240K	boost-libs/libboost_fiber.a
416K	boost-libs/libboost_filesystem.a
880K	boost-libs/libboost_graph.a
172K	boost-libs/libboost_iostreams.a
2,1M	boost-libs/libboost_locale.a
580K	boost-libs/libboost_math_c99.a
488K	boost-libs/libboost_math_c99f.a
504K	boost-libs/libboost_math_c99l.a
2,8M	boost-libs/libboost_math_tr1.a
2,8M	boost-libs/libboost_math_tr1f.a
2,8M	boost-libs/libboost_math_tr1l.a
216K	boost-libs/libboost_prg_exec_monitor.a
1,6M	boost-libs/libboost_program_options.a
84K	boost-libs/libboost_random.a
2,7M	boost-libs/libboost_regex.a
1,2M	boost-libs/libboost_serialization.a
24K	boost-libs/libboost_stacktrace_addr2line.a
24K	boost-libs/libboost_stacktrace_backtrace.a
16K	boost-libs/libboost_stacktrace_basic.a
4,0K	boost-libs/libboost_stacktrace_noop.a
4,0K	boost-libs/libboost_system.a
2,3M	boost-libs/libboost_test_exec_monitor.a
56K	boost-libs/libboost_timer.a
2,3M	boost-libs/libboost_unit_test_framework.a
4,6M	boost-libs/libboost_wave.a
780K	boost-libs/libboost_wserialization.a
```
## 11. Найдите топ-10 самых "тяжёлых".
```bash
du -h ~/boost-libs/*.a | sort -hr | head -n 10
```
```bash
4,6M	boost-libs/libboost_wave.a
2,8M	boost-libs/libboost_math_tr1l.a
2,8M	boost-libs/libboost_math_tr1f.a
2,8M	boost-libs/libboost_math_tr1.a
2,7M	boost-libs/libboost_regex.a
2,3M	boost-libs/libboost_unit_test_framework.a
2,3M	boost-libs/libboost_test_exec_monitor.a
2,1M	boost-libs/libboost_locale.a
1,6M	boost-libs/libboost_program_options.a
1,2M	boost-libs/libboost_serialization.a
```
