import hashlib
class RayaneCoinBlock:
  def __init__(self, previous_block_hash, transaction_list):
      self.previous_block_hash = previous_block_hash
      self.transaction_list = transaction_list
      self.block_data = "-".join(transaction_list) + "-" + previous_block_hash
      self.block_hash = hashlib.sha256(self.block_data.encode()).hexdigest()
      self.hex_digest = hashlib.sha256(self.block_data.encode()).hexdigest() 
t1 = "Anna sends 12.32 RN to Mike"
t2 = "Bob sends 0.02 RN to George"
t3 = "Mom sends 23 RN to Dad"
t4 = "Sister sends 1.2 RN to Brother"
t5 = "Biden sends 0.2 RN to TRump"
t6 = "Trump sends 2.9 RN to Rayane"
initial_block = RayaneCoinBlock("Initial String",[t1, t2])
second_block = RayaneCoinBlock(initial_block.block_hash,[t3, t4])
print(initial_block.block_data)
print(initial_block.hex_digest)

second_block = RayaneCoinBlock(initial_block.block_hash,[t3, t4])

print(second_block.block_data)
print(second_block.hex_digest)

third_block = RayaneCoinBlock(second_block.block_hash, [t5, t6])

print(third_block.block_data)
print(third_block.hex_digest)

