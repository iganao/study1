# study
独学

◯取得した数字N。N週間後は何日後か。
input_line = gets.to_i
puts input_line * 7


◯N人で試合をした時の試合数。N ✖︎ (N - 1) / 2で出る。
N = gets.to_i
puts N * (N - 1) / 2

◯
b
n
a_1
a_2
:
a_n
ここで、b は当選番号、n は購入した宝くじの数、a_1,…,a_n は購入した宝くじ券の番号をそれぞれ表します。
1等の場合: first
前後賞の場合: adjacent
2等の場合: second
3等の場合: third
それ以外（外れ）の場合: blank

b = gets.to_i
n = gets.to_i
a = n.times.map { gets.to_i }

a.each do |e|
  result = 'blank'

  if e == b
    result = 'first'
  elsif e + 1 == b || e - 1 == b
    result = 'adjacent'
  elsif e % 10_000 == b % 10_000
    result = 'second'
  elsif e % 1000 == b % 1000
    result = 'third'
  end

  puts result
end
