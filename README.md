# Pemdas_Itenas
import pandas as pd

# Data awal
data = {'Nama': ['John', 'Jane', 'Bob', 'Alice'],
        'Usia': [25, 35, 30, 28],
        'Gaji': [50000, 60000, 70000, 55000]}

# Membuat DataFrame
df = pd.DataFrame(data)
print("DataFrame awal:")
print(df)
# Peningkatan gaji sebesar 5%
for i in range(len(df)):
    df.at[i, 'Gaji'] = (lambda x: x * 1.05)(df.at[i, 'Gaji'])

print("\nDataFrame setelah peningkatan 5%:")
print(df)
print("\nRingkasan perubahan setelah peningkatan 5%:")
for i in range(len(data['Nama'])):
    print(f"Gaji {data['Nama'][i]} sebelum: {data['Gaji'][i]}, setelah: {df.at[i, 'Gaji']}")
# Peningkatan tambahan 2% untuk karyawan berusia di atas 30 tahun
for i in range(len(df)):
    if df.at[i, 'Usia'] > 30:
        df.at[i, 'Gaji'] = (lambda x: x * 1.02)(df.at[i, 'Gaji'])

print("\nDataFrame setelah peningkatan tambahan 2% untuk usia di atas 30:")
print(df)
print("\nRingkasan perubahan setelah peningkatan tambahan:")
for i in range(len(data['Nama'])):
    if data['Usia'][i] > 30:
        print(f"Gaji {data['Nama'][i]} dengan usia {data['Usia'][i]} sebelum: {data['Gaji'][i]}, setelah: {df.at[i, 'Gaji']}")
