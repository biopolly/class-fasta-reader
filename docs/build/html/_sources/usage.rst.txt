Примеры использования
=====================

Работа с отдельными последовательностями
-----------------------------------------

.. code-block:: python

   from bioseq.sequence import Seq
   
   # Создание последовательности
   seq = Seq("ATCGATCG", "test_sequence")
   print(seq)  # >test_sequence\nATCGATCG
   
   # Определение типа
   print(seq.alphabet())  # 'nucleotide'
   
   # Расчет GC-состава
   print(seq.gc_content())  # 50.0

Чтение FASTA файлов
-------------------

.. code-block:: python

   from bioseq.fasta_reader import FastaReader
   
   reader = FastaReader()
   
   # Проверка формата файла
   if reader.is_fasta("sequences.fasta"):
       # Чтение записей
       for record in reader.read_records("sequences.fasta"):
           print(f"Header: {record.header}")
           print(f"Type: {record.alphabet()}")
           print(f"Length: {len(record)}")
   
   # Получение статистики
   stats = reader.get_statistics("sequences.fasta")
   print(f"Total records: {stats['total_records']}")

Обработка данных
----------------

.. code-block:: python

   # Фильтрация последовательностей по длине
   reader = FastaReader("sequences.fasta")
   long_sequences = [
       record for record in reader.read_records() 
       if len(record) > 100
   ]
   
   # Разделение по типу
   nucleotides = []
   proteins = []
   
   for record in reader.read_records():
       if record.alphabet() == 'nucleotide':
           nucleotides.append(record)
       elif record.alphabet() == 'protein':
           proteins.append(record)