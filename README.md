# golden_section

matlab_code 

function  d=golden_section (x_L,x_U,k,N)  %%% x_L, x_U, N  (x_U-x_L)  最終可忍受的區間 N itrativ


f_L=CF(x_L);


f_U=CF(x_U);


tau=0.381966; %dacay_ratio


x_1=(1-tau)*x_L+tau*x_U; %%左邊的點


x_2=(1-tau)*x_U+tau*x_L; %%右邊的點


f_1=CF(x_1);


f_2=CF(x_2);


while k<N


if f_1>f_2 


x_L=x_1;

f_L=f_1;

x_1=x_2;

f_1=f_2;

x_2=(1-tau)*x_U+tau*x_L;

f_2=CF(x_2);

elseif f_1<f_2

x_U=x_2;

f_U=f_2;

x_2=x_1;

f_2=f_1;

x_1=(1-tau)*x_L+tau*x_U;

f_1=CF(x_1);

end

k=k+1;

golden_section (x_L,x_U,k,N)

end

f_1
f_2
end

function a=CF(x)
a=; your wanted cost function 
end
