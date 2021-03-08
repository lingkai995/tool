':log info "start download all_cn_cidr.rsc ..."
/tool fetch http-method=get url=https://goodffd.github.io/tool/all_cn_cidr.rsc
:log info "all_cn_cidr.rsc downloaded."
/file {
  :local addrFile
  :local fileSize
  :set addrFile [find where name="all_cn_cidr.rsc"]
  :set fileSize [get $addrFile size]
  :if ($fileSize > 170000) do={
    /import file=all_cn_cidr.rsc
    :log info "CN address list updated!"
  }
}'
