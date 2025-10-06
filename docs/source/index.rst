BioSeq Analyzer Documentation
=============================

BioSeq Analyzer - это Python библиотека для работы с биологическими последовательностями в формате FASTA.

.. toctree::
   :maxdepth: 2
   :caption: Содержание:

   modules
   usage

Основные возможности
--------------------

* Чтение FASTA файлов
* Определение типа последовательности (нуклеотид/протеин)
* Статистический анализ



Класс Seq
--------------------
Класс Seq представляет биологическую последовательность (нуклеотидную или аминокислотную).

Параметры:
sequence (str): нуклеотидная или аминокислотная последовательность

header (str): заголовок FASTA записи (информация о последовательности)

Методы:
__str__(): возвращает строковое представление последовательности в формате FASTA

__len__(): возвращает длину последовательности

alphabet(): определяет тип последовательности (нуклеотидная, белковая или неизвестная)



Класс FastaReader
--------------------
Класс для чтения и анализа FASTA файлов.

Методы:
is_fasta(filename): проверяет, является ли файл корректным FASTA файлом

read_records(filename): читает FASTA файл и возвращает генератор объектов Seq

Быстрый старт
-------------

.. code-block:: python

   from bioseq import FastaReader, Seq
   
   # Создание последовательности
   seq = Seq("ATCG", "test_sequence")
   print(f"Type: {seq.alphabet()}")
   print(f"Length: {len(seq)}")
   
   # Чтение FASTA файла
   reader = FastaReader("sequences.fasta")
   for record in reader.read_records():
       print(record.header)

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
