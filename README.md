# apply-for-research-intern-in-PTM
1-hour screen test
function result=ExtractMthEnd_1(dat)
data=dat(:,2)
siz=size(data);
poi=[1]
deter=isnan(dat(:,3))
for i=1:siz-1
    if data(i+1)>data(i)+31
        poi(end+1)=i
        j=i
        while deter(j)==1 & j-1>0
            j=j-1
            poi(end)=j
        end
        if poi(end)==poi(end-1)
            poi(end)=i
        end
    end
    i=i+1;
end
si=size(data)
poi(end+1)=si(1)
poi(1)=[]
result=dat(poi,:)
return
