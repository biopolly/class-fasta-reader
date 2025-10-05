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
* Расчет GC-состава
* Статистический анализ

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